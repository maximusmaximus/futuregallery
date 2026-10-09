# Draft schema (pending questions 35-42)

Names are illustrative. Types assume Postgres.

```sql
create table exhibits (
  id uuid primary key,
  owner_id uuid not null,
  title text not null,
  slug text not null,
  banner_url text,
  summary text,
  visibility text not null check (visibility in ('public', 'private')),
  entry_code text not null,
  opens_at timestamptz,
  closes_at timestamptz,
  created_at timestamptz not null default now()
);

create table objects (
  id uuid primary key,
  exhibit_id uuid not null references exhibits(id),
  title text,
  status text not null check (status in ('draft', 'needs_scans', 'ready')),
  scan_count int not null default 0,
  angle_count int not null default 0,
  diversity_score real,
  created_at timestamptz not null default now()
);

create table object_scans (
  id uuid primary key,
  object_id uuid not null references objects(id),
  image_url text not null,
  mask_url text,
  embedding vector(512),
  pose jsonb,
  created_by uuid,
  created_at timestamptz not null default now()
);

create table object_content (
  id uuid primary key,
  object_id uuid not null references objects(id),
  kind text not null,
  body jsonb not null,
  locale text not null default 'en'
);

create table selections (
  id uuid primary key,
  exhibit_id uuid not null references exhibits(id),
  user_id uuid,
  session_id text,
  object_ids uuid[] not null,
  created_at timestamptz not null default now()
);
```

Vector dimension, storage bucket layout, and auth user table depend on the database and matching answers.
