# SelinTour API

<hr />

### Settings CRUD

<ul>
  <li>GET => LIST `/api/settings`</li>
  <li>GET => ONE `/api/settings/[slug]`</li>
  <li>POST => CREATE `/api/settings/create`</li>
  <li>PUT => UPDATE `/api/settings/update?id=1`</li>
  <li>DELETE => DELETE `/api/settings/delete?id=1`</li>
</ul>

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

<ul>
  <li>GET => LIST `/api/category`</li>
  <li>GET => ONE `/api/category/[id]`</li>
  <li>POST => CREATE `/api/category/create`</li>
  <li>PUT => UPDATE `/api/category/update?id=1`</li>
  <li>DELETE => DELETE `/api/category/delete?id=1`</li>
</ul>

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

<ul>
  <li>GET => LIST `/api/sub-category?category_id=1`</li>
  <li>GET => ONE `/api/sub-category/[id]`</li>
  <li>POST => CREATE `/api/sub-category/create?category_id=1`</li>
  <li>PUT => UPDATE `/api/sub-category/update?id=1`</li>
  <li>DELETE => DELETE `/api/sub-category/delete?id=1`</li>
</ul>

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
