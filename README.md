# SelinTour API

---

- `*` is REQUIRED field

- All statuses (by default 1)
  0 => inactive
  1 => active

- todo...

---

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
  *slug: string;        // on update don't edit slug field
  status: number;       // byDefault 1
  creaetd_at: DATE;
  updated_at: DATE;
}
```

---

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
  *title_uz: string;
  *title_ru: string;
  *title_en: string;
  status: number;  // byDefault 1
  creaetd_at: DATE;
  updated_at: DATE;
}
```

---

### SubCategories CRUD

<ul>
  <li>GET => LIST <code>/api/sub-category</code></li>
  <li>GET => ONE GROUP <code>/api/sub-category?category_id=1</code></li>
  <li>POST => CREATE <code>/api/sub-category/create?category_id=1</code></li>
  <li>PUT => UPDATE <code>/api/sub-category/update?id=1</code></li>
  <li>DELETE => DELETE <code>/api/sub-category/delete?id=1</code></li>
</ul>

```JS
{
  id: number;
  *title_uz: string;
  *title_ru: string;
  *title_en: string;
  *category_id: number;
  status: number; // byDefault 1
  creaetd_at: DATE;
  updated_at: DATE;
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
  *title_uz: string;
  *title_ru: string;
  *title_en: string;
  *description_uz: string;
  *description_ru: string;
  *description_en: string;
  sub_category_ids: number[]; // [1, 2, 3]
  status: number;             // byDefault 1
  creaetd_at: DATE;
  updated_at: DATE;
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
  content_uz: string;       // unlimited size
  content_ru: string;       // unlimited size
  content_en: string;       // unlimited size
  link: string;
  *slug: string;            // on update don't edit slug field
  status: number;           // byDefault 1
  file_ids: number[];       // example: [1, 2, 3]
  files: [file urls];       // example: ["https...jpg", "https...png", "https...svg"]
  checked_list: string[];   // ["...", "..."]
  creaetd_at: DATE;
  updated_at: DATE;
}
```

<hr/>

### Countries CRUD

<ul>
  <li>GET => LIST <code>/api/country</code></li>
  <li>GET => ONE <code>/api/country/[slug]</code></li>
  <li>POST => CREATE <code>/api/country/create</code></li>
  <li>PUT => UPDATE <code>/api/country/update?id=1</code></li>
  <li>DELETE => DELETE <code>/api/country/delete?id=1</code></li>
</ul>

```JS
{
  id: number;
  status: number;
  *title_uz: string;
  *title_ru: string;
  *title_en: string;
  creaetd_at: DATE;
  updated_at: DATE;
}
```

---

### Testimonials CRUD

<ul>
  <li>GET => LIST <code>/api/testimonials</code></li>
  <li>GET => ONE <code>/api/testimonials/[id]</code></li>
  <li>POST => CREATE <code>/api/testimonials/create</code></li>
  <li>PUT => UPDATE <code>/api/testimonials/update?id=1</code></li>
  <li>DELETE => DELETE <code>/api/testimonials/delete?id=1</code></li>
</ul>

```JS
{
  id: number;
  name: string;
  user_id: number;
  *comment: string;
  *rate: number;                // 0 | 1 | 2 | 3 | 4 | 5
  top: number;                  // 0 | 1 => byDefault 1
  status: number;               // byDefault 1
  // *file_id: number;          // example: 1
  // file: fileUrl;             // example: "https...jpg"
  creaetd_at: DATE;
  updated_at: DATE;
}
```

---

### Destinations CRUD

<ul>
  <li>GET => LIST <code>/api/destination</code></li>
  <li>GET => ONE <code>/api/destination/[id]</code></li>
  <li>POST => CREATE <code>/api/destination/create</code></li>
  <li>PUT => UPDATE <code>/api/destination/update?id=1</code></li>
  <li>DELETE => DELETE <code>/api/destination/delete?id=1</code></li>
</ul>

```JS
{
  id: number;
  *title_uz: string;
  *title_ru: string;
  *title_en: string;
  *description_uz: string;
  *description_ru: string;
  *description_en: string;
  top: number;                  // 0 | 1 => byDefault 1
  status: number;               // byDefault 1
  tour_count: number;           // auto generate joined tours count
  sub_category_ids: number[];   // [1, 2, 3]
  cauntry_ids: number[];        // [1, 2, 3]
  *file_id: number;             // example: 1
  file: fileUrl;                // example: "https...jpg"
  published_at: DATE;
  creaetd_at: DATE;
  updated_at: DATE;
}
```

---

### Tour includes CRUD

<ul>
  <li>GET => LIST <code>/api/tour-include</code></li>
  <li>GET => ONE <code>/api/tour-include/[id]</code></li>
  <li>POST => CREATE <code>/api/tour-include/create</code></li>
  <li>PUT => UPDATE <code>/api/tour-include/update?id=1</code></li>
  <li>DELETE => DELETE <code>/api/tour-include/delete?id=1</code></li>
</ul>

```JS
{
  id: number;
  *title_uz: string;
  *title_ru: string;
  *title_en: string;
  status: number;     // byDefault 1
  creaetd_at: DATE;
  updated_at: DATE;
}
```

---

### Tour Itenirary CRUD

<ul>
  <li>GET => LIST <code>/api/tour-itenirary-plan</code></li>
  <li>GET => ONE <code>/api/tour-itenirary-plan/[id]</code></li>
  <li>POST => CREATE <code>/api/tour-itenirary-plan/create</code></li>
  <li>PUT => UPDATE <code>/api/tour-itenirary-plan/update?id=1</code></li>
  <li>DELETE => DELETE <code>/api/tour-itenirary-plan/delete?id=1</code></li>
</ul>

```JS
{
  id: number;
  *title_uz: string;
  *title_ru: string;
  *title_en: string;
  *description_uz: string;
  *description_ru: string;
  *description_en: string;
  status: number;           // byDefault 1
  creaetd_at: DATE;
  updated_at: DATE;
}
```

---

### Tours CRUD

<ul>
  <li>GET => LIST <code>/api/tour</code></li>
  <li>GET => ONE <code>/api/tour/[id]</code></li>
  <li>POST => CREATE <code>/api/tour/create</code></li>
  <li>PUT => UPDATE <code>/api/tour/update?id=1</code></li>
  <li>DELETE => DELETE <code>/api/tour/delete?id=1</code></li>
</ul>

```JS

// filter params
{
  id: number;

  type: "new" | "top" | "discount" | "popular" // popular => maxLiked // byDefault "new"

  destination_ids: string;      // "1,2,3"

  sub_category_ids: string;     // "1,2,3"

  country_ids: string;          // "1,2,3"

  begin_people_count: number;
  end_people_count: number;

  begin_date: string;           // 11.10.2024
  end_date: string;             // 29.11.2024

  begin_price: number;
  end_price: number;

}

// data
{
  id: number;
  *price: number;
  discount_price: number;
  *title_uz: string;
  *title_ru: string;
  *title_en: string;
  description_uz: string;
  description_ru: string;
  description_en: string;
  content_uz: string;           // size unlimited
  content_ru: string;           // size unlimited
  content_en: string;           // size unlimited
  rate_count: number;           // 44
  avg_rate: number;             // 4.4
  duration_days: number;
  employe_id: number;
  cauntry_ids: number[];        // [1, 2, 3]
  testimonial_ids: number[];    // [1, 2, 3]
  sub_category_ids: number[];   // [1, 2, 3]
  itenirary_plan_ids: number[]; // [1, 2, 3]
  *file_ids: number;            // example: [1, 2, 3]
  files: [fileUrls];            // example: ["https...jpg", "https...jpg", "https...jpg"...]
  top: number;                  // 0 | 1 => byDefault 1
  status: number;               // byDefault 1
  creaetd_at: DATE;
  updated_at: DATE;
  // isLidked...
  // lidked_count...
}
```

---

<br/>
<br/>
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
  birth_date: DATE;         // 24.01.1998
  *email: string;
  *phone: string;
  *country_id: number;      // from /api/country
  region: string;
  *password: string;
  *repeat_password: string;
}
```

---

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

---
