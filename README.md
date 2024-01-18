# SelinTour API

<hr />

### Settings CRUD

GET => LIST `/api/settings`
GET => ONE `/api/settings/[slug]`
POST => CREATE `/api/settings/create`
PUT => UPDATE `/api/settings/update?id=1`
DELETE => DELETE `/api/settings/delete?id=1`

```JS
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
  status: number;
  creaetd_at: Date;
  updated_at: Date;
}
```

<hr />

### Categories CRUD

GET => LIST `/api/category`
GET => ONE `/api/category/[id]`
POST => CREATE `/api/category/create`
PUT => UPDATE `/api/category/update?id=1`
DELETE => DELETE `/api/category/delete?id=1`

```JS
{
  id: number;
  title_uz: string;
  title_ru: string;
  title_en: string;
  status: number;
}
```

<hr />

### SubCategories CRUD

GET => LIST `/api/sub-category?category_id=1`
GET => ONE `/api/sub-category/[id]`
POST => CREATE `/api/sub-category/create?category_id=1`
PUT => UPDATE `/api/sub-category/update?id=1`
DELETE => DELETE `/api/sub-category/delete?id=1`

```JS
{
  id: number;
  title_uz: string;
  title_ru: string;
  title_en: string;
  category_id: number;
  status: number;
}
```
