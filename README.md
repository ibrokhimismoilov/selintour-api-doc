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

### FAQ CRUD

<ul>
  <li>GET => LIST <code>/api/faq</code></li>
  <li>GET => ONE GROUP <code>/api/faq?sub_category_id=1</code></li>
  <li>POST => CREATE <code>/api/faq/create?sub_category_id=1</code></li>
  <li>PUT => UPDATE <code>/api/faq/update?id=1</code></li>
  <li>DELETE => DELETE <code>/api/faq/delete?id=1</code></li>
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
  sub_category_ids: number[]; // [1, 2, 3]
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
  checked_list: string[];  // ["...", "..."]
  creaetd_at: Date;
  updated_at: Date;
}
```

<hr/>

### Countries CRUD

<ul>
  <li>GET => LIST <code>/api/country</code></li>
</ul>

```JS
{
  id: number;
  title_uz: string;
  title_ru: string;
  title_en: string;
}
```

<br/>
<br/>
================================================================================
<br/>
<br/>

### AUTH REGISTER

<ul>
  <li>POST => REGISTER <code>/api/auth/register</code></li>
  // CRUD is coming soon
</ul>

```JS
{
  id: number;
  *first_name: string;
  last_name: string;
  birth_date: DATE; // 24.01.1998
  *email: string;
  *phone: string;
  *country_id: number; // from /api/country
  region: string;
  *password: string;
  *repeat_password: string;
}
```

<hr />

### AUTH LOGIN

<ul>
  <li>POST => LOGIN <code>/api/auth/login</code></li>
</ul>

```JS
{
  *email: string;
  *password: string;
}
```

<br/>
<br/>
================================================================================
<br/>
<br/>
