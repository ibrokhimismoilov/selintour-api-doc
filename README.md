# SelinTour API

## Settings CRUD

<hr />

#### GET List /api/settings

```JavaScript
[
  {
    id: number;
    title_uz: string;
    title_ru: string;
    title_en: string;
    description_uz: string;
    description_ru: string;
    description_en: string;
    link: string;
    alias: string;
    slug: string;
    creaetd_at: Date;
    updated_at: Date;
  }
]
```

#### GET One /api/settings/[slug]

```JavaScript
{
  id: number;
  title_uz: string;
  title_ru: string;
  title_en: string;
  description_uz: string;
  description_ru: string;
  description_en: string;
  link: string;
  alias: string;
  slug: string;
  creaetd_at: Date;
  updated_at: Date;
}
```

#### POST Create /api/settings/create

```JavaScript
{
  title_uz: string;
  title_ru: string;
  title_en: string;
  description_uz: string;
  description_ru: string;
  description_en: string;
  link: string;
  alias: string;
  slug: string;
}
```

#### PUT Update /api/settings/update?id=1

```JavaScript
{
  id: number;
  title_uz: string;
  title_ru: string;
  title_en: string;
  description_uz: string;
  description_ru: string;
  description_en: string;
  link: string;
  alias: string;
  slug: string;
}
```

#### PUT Delete /api/settings/delete?id=1

<hr />
