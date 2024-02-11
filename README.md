# SelinTour API

---

- `*` is REQUIRED field

- All statuses (by default 1)
  0 => inactive
  1 => active

  - barcha getAll API larda status 1 bo'lganlari qaytadi.
  - Qachonki {status: 0} param yuborilsa barchasi qaytadi.

- Barcha GET LIST lar pagination bo'lishi kerak va quyidagi paramlarni qa'bul qilsin

  - page: number
  - size: number

- Barcha Create & Update larda

  - fileId: 1 => ketgan bo'lsa getOneAPIda { file: FILE_DTO }
  - fileIds: [1, 2] => ketgan bo'lsa getOneAPIda { files: [FILE_DTO, FILE_DTO...] }

  - categoryId: 1 => ketgan bo'lsa getOneAPIda { category: CATEGORY_DTO }
  - categoryIds: [1, 2] => ketgan bo'lsa getOneAPIda { categories: [CATEGORY_DTO, CATEGORY_DTO...] }

  - subCategoryId: 1 => ketgan bo'lsa getOneAPIda { subCategory: SUB_CATEGORY_DTO }
  - subcategoryIds: [1, 2] => ketgan bo'lsa getOneAPIda { subCategories: [SUB_CATEGORY_DTO, SUB_CATEGORY_DTO...] }

  - countryId: 1 => ketgan bo'lsa getOneAPIda { country: COUNTRY_DTO }
  - countryIds: [1, 2] => ketgan bo'lsa getOneAPIda { countries: [COUNTRY_DTO, COUNTRY_DTO...] }

  - checkedListId: 1 => ketgan bo'lsa getOneAPIda { checkedList: PAGE_CHECKED_LIST_DTO }
  - checkedListIds: [1, 2] => ketgan bo'lsa getOneAPIda { checkedLists: [PAGE_CHECKED_LIST_DTO, PAGE_CHECKED_LIST_DTO...] }

  - testimonialId: 1 => ketgan bo'lsa getOneAPIda { testimonial: TESTIMONIAL_DTO }
  - testimonialIds: [1, 2] => ketgan bo'lsa getOneAPIda { testimonials: [TESTIMONIAL_DTO, TESTIMONIAL_DTO...] }

  - destinationId: 1 => ketgan bo'lsa getOneAPIda { destination: DESTINATION_DTO }
  - destinationIds: [1, 2] => ketgan bo'lsa getOneAPIda { destinations: [DESTINATION_DTO, DESTINATION_DTO...] }

  - userId: 1 => ketgan bo'lsa getOneAPIda { user: USER_DTO }
  - userIds: [1, 2] => ketgan bo'lsa getOneAPIda { users: [USER_DTO, USER_DTO...] }

  - employeeId: 1 => ketgan bo'lsa getOneAPIda { employee: USER_DTO }
  - employeeIds: [1, 2] => ketgan bo'lsa getOneAPIda { employees: [USER_DTO, USER_DTO...] }

  - includeIds: [1, 2] => ketgan bo'lsa getOneAPIda { includes: [TOUR_INCLUDE_DTO, TOUR_INCLUDE_DTO...] }
  - noIncludeIds: [1, 2] => ketgan bo'lsa getOneAPIda { noIncludes: [TOUR_INCLUDE_DTO, TOUR_INCLUDE_DTO...] }

  - itineraryPlanIds: [1, 2] => ketgan bo'lsa getOneAPIda { itineraryPlans: [TOUR_ITENERARRY_DTO, TOUR_ITENERARRY_DTO...] }

---

### File CRUD [open => POST_CREATE]

<ul>
  <li>POST => CREATE <code>/api/files/create?{type}</code></li>
</ul>

```JS

{
  method: "post",
  url: "/api/files/create",
  data: FORMDATA,           // { file: binar }
  headers: {
    params: {
      type: number;         // 1 | 2 | 3 | 4
    },
    "Content-Type": "multipart/form-data",
  },
}

```

<ul>
  <li>GET => LIST <code>/api/files?{type}</code></li>
  <li>GET => ONE <code>/api/files?{fileId}</code></li>
  <li>DELETE => DELETE <code>/api/files/delete?{fileId}</code></li>
</ul>

```JS

// params
{
  type: number, // 1 | 2 | 3 | 4
}

// data
[
  {
    size: number, // 10240 bytes
    type: string, // fileType => images
    name: string, // fileName.type
    fileId: number;
    orgUrl: "https://...",
    src: {
      thumb: "https://..." // height: 300px
      large: "https://..." // height: 2400px
    }
  }
]
```

### Countries CRUD [open => GET_LIST]

<ul>
  <li>GET => LIST <code>/api/country</code></li>
  <li>GET => ONE <code>/api/country/[id]</code></li>
  <li>POST => CREATE <code>/api/country/create</code></li>
  <li>PUT => UPDATE <code>/api/country/update?{id}</code></li>
  <li>DELETE => DELETE <code>/api/country/delete?{id}</code></li>
</ul>

```JS
{
  id: number;
  status: number;
  *titleUz: string;
  *titleRu: string;
  *titleEn: string;
  creaetdAt: DATE;
  updatedAt: DATE;
}
```

---

### Categories CRUD [open => GET_LIST]

<ul>
  <li>GET => LIST <code>/api/category</code> </li>
  <li>GET => ONE <code>/api/category/[categorySlug]</code></li>
  <li>POST => CREATE <code>/api/category/create</code></li>
  <li>PUT => UPDATE <code>/api/category/update?{id}</code></li>
  <li>DELETE => DELETE <code>/api/category/delete?{id}</code></li>
</ul>

```JS
{
  id: number;
  *categorySlug: string;
  *titleUz: string;
  *titleRu: string;
  *titleEn: string;
  status: number;  // byDefault 1
  creaetdAt: DATE;
  updatedAt: DATE;
}
```

---

### SubCategories CRUD [open => GET_LIST]

<ul>
  <li>GET => LIST <code>/api/sub-category</code></li>
  <li>GET => LIST BY CATEGORY <code>/api/sub-category?{categorySlug}</code></li>
  <li>GET => ONE <code>/api/sub-category/[subCategoryId]</code></li>
  <li>POST => CREATE <code>/api/sub-category/create</code></li>
  <li>PUT => UPDATE <code>/api/sub-category/update?{id}</code></li>
  <li>DELETE => DELETE <code>/api/sub-category/delete?{id}</code></li>
</ul>

```JS
{
  id: number;
  *titleUz: string;
  *titleRu: string;
  *titleEn: string;
  *categorySlug: string;
  status: number; // byDefault 1
  creaetdAt: DATE;
  updatedAt: DATE;
}
```

<hr/>

### FAQ CRUD [open => GET_LIST, GET_ONE_GROUP]

<ul>
  <li>GET => LIST <code>/api/faq</code></li>
  <li>GET => ONE GROUP <code>/api/faq?{subCategoryId}</code></li>
  <li>POST => CREATE <code>/api/faq/create?{subCategoryId}</code></li>
  <li>PUT => UPDATE <code>/api/faq/update?{id}</code></li>
  <li>DELETE => DELETE <code>/api/faq/delete?{id}</code></li>
</ul>

```JS
{
  id: number;
  *titleUz: string;
  *titleRu: string;
  *titleEn: string;
  *descriptionUz: string;
  *descriptionRu: string;
  *descriptionEn: string;
  subcategoryIds: number[];   // [1, 2, 3]
  status: number;             // byDefault 1
  creaetdAt: DATE;
  updatedAt: DATE;
}
```

---

### Testimonials CRUD [open => GET_LIST, GET_ONE]

<ul>
  <li>GET => LIST <code>/api/testimonials</code></li>
  <li>GET => ONE <code>/api/testimonials/[id]</code></li>
  <li>POST => CREATE <code>/api/testimonials/create</code></li>
  <li>PUT => UPDATE <code>/api/testimonials/update?{id}</code></li>
  <li>DELETE => DELETE <code>/api/testimonials/delete?{id}</code></li>
</ul>

```JS
{
  id: number;
  *rate: number;                // 0 ... 2 ... 3.5 ...  5
  *userId: number;
  *comment: string;
  top: number;                  // 0 | 1 => byDefault 1
  status: number;               // byDefault 1
  creaetdAt: DATE;
  updatedAt: DATE;
}
```

---

### Settings CRUD [open => GET_LIST, GET_ONE]

<ul>
  <li>GET => LIST <code>/api/settings</code></li>
  <li>GET => ONE <code>/api/settings/[slug]</code></li>
  <li>POST => CREATE <code>/api/settings/create</code></li>
  <li>PUT => UPDATE <code>/api/settings/update?{id}</code></li>
  <li>DELETE => DELETE <code>/api/settings/delete?{id}</code></li>
</ul>

```JS
{
  id: number;
  titleUz: string;
  titleRu: string;
  titleEn: string;
  descriptionUz: string;
  descriptionRu: string;
  descriptionEn: string;
  link: string;
  alias: string;
  *slug: string;        // on update don't edit slug field
  status: number;       // byDefault 1
  fileId: number;      // example: 1
  creaetdAt: DATE;
  updatedAt: DATE;
}
```

---

### PageCheckedList CRUD [open => GET_LIST, GET_ONE_GROUP]

<ul>
  <li>GET => LIST <code>/api/page-checked-list</code></li>
  <li>GET => ONE <code>/api/page-checked-list/[id]</code></li>
  <li>POST => CREATE <code>/api/page-checked-list/create</code></li>
  <li>PUT => UPDATE <code>/api/page-checked-list/update?{id}</code></li>
  <li>DELETE => DELETE <code>/api/page-checked-list/delete?{id}</code></li>
</ul>

```JS
{
  id: number;
  *contentUz: string;           // unlimited size
  *contentRu: string;           // unlimited size
  *contentEn: string;           // unlimited size
  status: number;                // byDefault 1
  creaetdAt: DATE;
  updatedAt: DATE;
}
```

---

### Page CRUD [open => GET_LIST, GET_ONE]

<ul>
  <li>GET => LIST <code>/api/page</code></li>
  <li>GET => ONE <code>/api/page/[slug]</code></li>
  <li>POST => CREATE <code>/api/page/create</code></li>
  <li>PUT => UPDATE <code>/api/page/update?{id}</code></li>
  <li>DELETE => DELETE <code>/api/page/delete?{id}</code></li>
</ul>

```JS
{
  id: number;
  titleUz: string;
  titleRu: string;
  titleEn: string;
  descriptionUz: string;
  descriptionRu: string;
  descriptionEn: string;
  contentUz: string;            // unlimited size
  contentRu: string;            // unlimited size
  contentEn: string;            // unlimited size
  link: string;
  *slug: string;                // on update don't edit slug field
  status: number;               // byDefault 1
  fileIds: number[];            // example: [1, 2, 3]
  files: [FILE_DTO];            // [FILE_DTO, FILE_DTO]
  checkedListIds: nummber[];    // [1, 2]
  creaetdAt: DATE;
  updatedAt: DATE;
}
```

---

### Destinations CRUD [open => GET_LIST, GET_ONE]

<ul>
  <li>GET => LIST <code>/api/destination</code></li>
  <li>GET => ONE <code>/api/destination/[id]</code></li>
  <li>POST => CREATE <code>/api/destination/create</code></li>
  <li>PUT => UPDATE <code>/api/destination/update?{id}</code></li>
  <li>DELETE => DELETE <code>/api/destination/delete?{id}</code></li>
</ul>

```JS
{
  id: number;
  *titleUz: string;
  *titleRu: string;
  *titleEn: string;
  *descriptionUz: string;
  *descriptionRu: string;
  *descriptionEn: string;
  top: number;                  // 0 | 1 => byDefault 1
  status: number;               // byDefault 1
  tourCount: number;            // auto generate when joined tours
  subCategoryIds: number[];     // [1, 2, 3]
  cauntryIds: number[];         // [1, 2, 3]
  *fileId: number;              // example: 1
  published_at: DATE;
  creaetdAt: DATE;
  updatedAt: DATE;
}
```

---

### Tour includes CRUD [open => GET_LIST, GET_ONE]

<ul>
  <li>GET => LIST <code>/api/tour-include</code></li>
  <li>GET => ONE <code>/api/tour-include/[id]</code></li>
  <li>POST => CREATE <code>/api/tour-include/create</code></li>
  <li>PUT => UPDATE <code>/api/tour-include/update?{id}</code></li>
  <li>DELETE => DELETE <code>/api/tour-include/delete?{id}</code></li>
</ul>

```JS
{
  id: number;
  *titleUz: string;
  *titleRu: string;
  *titleEn: string;
  status: number;     // byDefault 1
  creaetdAt: DATE;
  updatedAt: DATE;
}
```

---

### Tour Itenirary CRUD [open => GET_LIST, GET_ONE]

<ul>
  <li>GET => LIST <code>/api/tour-itenirary-plan</code></li>
  <li>GET => ONE <code>/api/tour-itenirary-plan/[id]</code></li>
  <li>POST => CREATE <code>/api/tour-itenirary-plan/create</code></li>
  <li>PUT => UPDATE <code>/api/tour-itenirary-plan/update?{id}</code></li>
  <li>DELETE => DELETE <code>/api/tour-itenirary-plan/delete?{id}</code></li>
</ul>

```JS
{
  id: number;
  *titleUz: string;
  *titleRu: string;
  *titleEn: string;
  *descriptionUz: string;
  *descriptionRu: string;
  *descriptionEn: string;
  status: number;           // byDefault 1
  creaetdAt: DATE;
  updatedAt: DATE;
}
```

---

### Tours CRUD [open => GET_LIST]

<ul>
  <li>GET => LIST <code>/api/tour</code></li>
  <li>GET => ONE <code>/api/tour/[id]</code></li>
  <li>POST => CREATE <code>/api/tour/create</code></li>
  <li>PUT => UPDATE <code>/api/tour/update?{id}</code></li>
  <li>DELETE => DELETE <code>/api/tour/delete?{id}</code></li>
</ul>

```JS

// filter params
{
  title: string;

  id: number;

  type: "new" | "top" | "discount" | "popular" // popular => maxLiked // byDefault "new"

  countryIds: string;          // "1,2,3"
  categoryIds: string;         // "1,2,3"
  destinationIds: string;      // "1,2,3"
  subCategoryIds: string;      // "1,2,3"

  beginPeopleCount: number;
  endPeopleCount: number;

  beginDate: string;           // 11.10.2024
  endDate: string;             // 29.11.2024

  beginPrice: number;
  endPrice: number;
}

// data
{
  id: number;
  *tour_number: string;
  *price: number;
  discountPrice: number;
  *titleUz: string;
  *titleRu: string;
  *titleEn: string;
  descriptionUz: string;
  descriptionRu: string;
  descriptionEn: string;
  contentUz: string;            // size unlimited
  contentRu: string;            // size unlimited
  contentEn: string;            // size unlimited
  peopleCount: number;
  rateCount: number;            // 44
  avgRate: number;              // 4.4
  durationDays: number;
  employeId: number;
  cauntryIds: number[];         // [1, 2, 3]
  testimonialIds: number[];     // [1, 2, 3]
  subCategoryIds: number[];     // [1, 2, 3]
  iteniraryPlanIds: number[];   // [1, 2, 3]
  includeIds: number[];         // [1, 2, 3]
  noIncludeIds: number[];       // [1, 2, 3]
  *fileIds: number[];           // example: [1, 2, 3]
  files: [FILE_DTO];            // example: [FILE_DTO, FILE_DTO, FILE_DTO...]
  top: number;                  // 0 | 1 => byDefault 1
  status: number;               // byDefault 1
  creaetdAt: DATE;
  updatedAt: DATE;
  // isLidked...
  // lidkedCount...
}
```

---

<br/>
<br/>
<br/>
<br/>

### CONTACT [open => POST_CREATE]

<ul>
  <li>GET => LIST <code>/api/contact</code></li>
  <li>POST => CREATE <code>/api/contact/create</code></li>
  <li>DELETE => DELETE <code>/api/contact/delete?{id}</code></li>
</ul>

```JS

{
  *name: string;
  *email: string;
  *phone: string;
  *message: string;
  company: string;
  userId: numbar;   // Agar regsitratsiyadan o'tgan bo'lsa userId qohib yuboriladi, USER CRUDga bog'lash shartmas.
  creaetdAt: DATE;
  updatedAt: DATE;
}

```

---

### AUTH REGISTER [open]

<ul>
  <li>POST => REGISTER <code>/api/auth/register</code></li>
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

### AUTH LOGIN [open]

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

### USER CRUD (FOR ADMIN)

<ul>
  <li>GET => LIST <code>/api/user</code></li>
  <li>GET => ONE <code>/api/user/[id]</code></li>
  <li>POST => CREATE <code>/api/user/create</code></li>
  <li>PUT => UPDATE <code>/api/user/update?{id}</code></li>
  <li>DELETE => DELETE <code>/api/user/delete?{id}</code></li>
</ul>

```JS


// filter params
{
  id: number;
  role: "USER" | "MODERATOR" | "ADMIN"
}

// data
{
  id: number;
  *firstName: string;
  lastName: string;
  birthDate: DATE;             // 24.01.1998
  *email: string;
  *phone: string;
  *countryId: number;           // from /api/country
  region: string;
  *password: string;
  *repeatPassword: string;
  fileId: number;               // example: 1
  status: number;               // byDefault 1
  role: string;                 // "USER" | "MODERATOR" | "ADMIN" => default "USER"
  token: string;                // JWT token
  creaetdAt: DATE;
  updatedAt: DATE;
  // profile...
}
```

### USER UPDATE

<ul>
  <li>PUT => UPDATE <code>/api/user/update?{userId}</code></li>
</ul>

```JS

// data
{
  id: number;
  birthDate: DATE;              // 24.01.1998
  lastName: string;
  *firstName: string;
  *email: string;
  *phone: string;
  *countryId: number;           // from /api/country
  region: string;
  fileId: number;               // example: 1
  role: string;                 // "USER" | "MODERATOR" | "ADMIN" => default "USER" | update only admin
  // status: number;            // byDefault 1
}
```

### USER PASSWORD UPDATE

<ul>
  <li>PUT => UPDATE <code>/api/user/update/password?userId=1</code></li>
</ul>

```JS

// data
{
  *currentPassword: string;
  *password: string;
  *repeatPassword: string;
}
```

### USER CRUD (FOR ADMIN)

<ul>
  <li>GET => LIST <code>/api/user</code></li>
  <li>GET => ONE <code>/api/user/[id]</code></li>
  <li>POST => CREATE <code>/api/user/create</code></li>
  <li>PUT => UPDATE <code>/api/user/update?{id}</code></li>
  <li>DELETE => DELETE <code>/api/user/delete?{id}</code></li>
</ul>

```JS

// filter params
{
  id: number;
  role: "USER" | "MODERATOR" | "ADMIN"
}

// data
{
  id: number;
  lastName: string;
  *firstName: string;
  *email: string;
  *phone: string;
  *countryId: number;           // from /api/country
  *password: string;
  *repeatPassword: string;
  birthDate: DATE;              // 24.01.1998
  region: string;
  fileId: number;               // example: 1
  status: number;               // byDefault 1
  role: string;                 // "USER" | "MODERATOR" | "ADMIN" => default "USER"
  token: string;                // JWT token
  creaetdAt: DATE;
  updatedAt: DATE;
  // profile...
}

```
