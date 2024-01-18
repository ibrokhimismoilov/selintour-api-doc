# SelinTour API

<hr />

### Settings CRUD

<ul>
  <li>GET => LIST <code>/api/settings</code></li>
  <li>GET => ONE <code>/api/settings/[slug]</code></li>
  <li>POST => CREATE <code>/api/settings/create</code></li>
  <li>PUT => UPDATE <code>/api/settings/update?id=1</code></li>
  <li>DELETE => DELETE <code>/api/settings/delete?id=1</code></li>
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
  slug: string;  // on update don't edit slug field
  status: number;  // bg default 1
  creaetd_at: Date;
  updated_at: Date;
}
```

<hr />

### Categories CRUD

<ul>
  <li>GET => LIST <code>/api/category</code> </li>
  <li>GET => ONE <code>/api/category/[id]</code></li>
  <li>POST => CREATE <code>/api/category/create</code></li>
  <li>PUT => UPDATE <code>/api/category/update?id=1</code></li>
  <li>DELETE => DELETE <code>/api/category/delete?id=1</code></li>
</ul>

```JS
{
  id: number;
  title_uz: string;
  title_ru: string;
  title_en: string;
  status: number;  // bg default 1
  creaetd_at: Date;
  updated_at: Date;
}
```

<hr />

### SubCategories CRUD

<ul>
  <li>GET => LIST <code>/api/sub-category?category_id=1</code></li>
  <li>GET => ONE <code>/api/sub-category/[id]</code></li>
  <li>POST => CREATE <code>/api/sub-category/create?category_id=1</code></li>
  <li>PUT => UPDATE <code>/api/sub-category/update?id=1</code></li>
  <li>DELETE => DELETE <code>/api/sub-category/delete?id=1</code></li>
</ul>

```JS
{
  id: number;
  title_uz: string;
  title_ru: string;
  title_en: string;
  category_id: number;
  status: number; // bg default 1
  creaetd_at: Date;
  updated_at: Date;
}
```

<hr/>

### Page CRUD

<ul>
  <li>GET => LIST <code>/api/page</code></li>
  <li>GET => ONE <code>/api/page/[slug]</code></li>
  <li>POST => CREATE <code>/api/page/create</code></li>
  <li>PUT => UPDATE <code>/api/page/update?id=1</code></li>
  <li>DELETE => DELETE <code>/api/page/delete?id=1</code></li>
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
  content_uz: string; // unlimited size
  content_ru: string; // unlimited size
  content_en: string; // unlimited size
  link: string;
  slug: string;  // on update don't edit slug field
  status: number;  // bg default 1
  file_ids: number[]; // example: [1, 2, 3]
  files: [file urls]; // example: ["https...jpg", "https...png", "https...svg"]
  creaetd_at: Date;
  updated_at: Date;
}
```

<hr/>

### Countries CRUD

<ul>
  <li>GET => LIST <code>/api/country</code></li>
  <!-- <li>GET => ONE <code>/api/country/[id]</code></li> -->
  <!-- <li>POST => CREATE <code>/api/country/create</code></li> -->
  <!-- <li>PUT => UPDATE <code>/api/country/update?id=1</code></li> -->
  <!-- <li>DELETE => DELETE <code>/api/country/delete?id=1</code></li> -->
</ul>

```JS
{
  id: number;
  title_uz: string;
  title_ru: string;
  title_en: string;
}
```
