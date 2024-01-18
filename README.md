# SelinTour API

<hr />

### Settings CRUD

<ul>
  <li>GET => LIST <kbd>/api/settings</kbd></li>
  <li>GET => ONE <kbd>/api/settings/[slug]</kbd></li>
  <li>POST => CREATE <kbd>/api/settings/create</kbd></li>
  <li>PUT => UPDATE <kbd>/api/settings/update?id=1</kbd></li>
  <li>DELETE => DELETE <kbd>/api/settings/delete?id=1</kbd></li>
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
  <li>GET => LIST <kbd>/api/category</kbd> </li>
  <li>GET => ONE </kbd>/api/category/[id]</kbd></li>
  <li>POST => CREATE </kbd>/api/category/create</kbd></li>
  <li>PUT => UPDATE </kbd>/api/category/update?id=1</kbd></li>
  <li>DELETE => DELETE </kbd>/api/category/delete?id=1</kbd></li>
</ul>

```JS
{
  id: number;
  title_uz: string;
  title_ru: string;
  title_en: string;
  status: number;  // bg default 1
}
```

<hr />

### SubCategories CRUD

<ul>
  <li>GET => LIST <kbd>/api/sub-category?category_id=1</kbd></li>
  <li>GET => ONE <kbd>/api/sub-category/[id]</kbd></li>
  <li>POST => CREATE <kbd>/api/sub-category/create?category_id=1</kbd></li>
  <li>PUT => UPDATE <kbd>/api/sub-category/update?id=1</kbd></li>
  <li>DELETE => DELETE <kbd>/api/sub-category/delete?id=1</kbd></li>
</ul>

```JS
{
  id: number;
  title_uz: string;
  title_ru: string;
  title_en: string;
  category_id: number;
  status: number; // bg default 1
}
```
