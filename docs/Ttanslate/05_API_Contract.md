# 🔌 نظام طلبات المطاعم

# 05 - عقد واجهات برمجة التطبيقات (API Contract)

---

# مقدمة

توضح هذه الوثيقة شكل البيانات المتبادلة بين الواجهة الأمامية (Frontend) والخادم (Backend).

يلتزم جميع أعضاء الفريق بنفس أسماء الحقول ونفس بنية البيانات طوال فترة تطوير المشروع.

أي تعديل في هذه الوثيقة يجب أن يتم الاتفاق عليه بين أعضاء الفريق قبل التنفيذ.

---

# عنوان الـ API

أثناء التطوير سيكون المسار الأساسي:

```

/api

```

---

# الوجبات (Meals)

## الحصول على جميع الوجبات

```

GET /api/meals

```

### البيانات المرجعة

```json
[
  {
    "id": 1,
    "name": "Classic Burger",
    "description": "Beef Burger with Cheese",
    "price": 120,
    "imageUrl": "burger.jpg",
    "categoryId": 1
  }
]
```

---

## الحصول على وجبة واحدة

```

GET /api/meals/{id}

```

### البيانات المرجعة

```json
{
  "id": 1,
  "name": "Classic Burger",
  "description": "Beef Burger with Cheese",
  "price": 120,
  "imageUrl": "burger.jpg",
  "categoryId": 1
}
```

---

# التصنيفات (Categories)

## الحصول على جميع التصنيفات

```

GET /api/categories

```

### البيانات المرجعة

```json
[
  {
    "id": 1,
    "name": "Burgers"
  },
  {
    "id": 2,
    "name": "Pizza"
  }
]
```

---

# الطلبات (Orders)

## إنشاء طلب جديد

```

POST /api/orders

```

### البيانات المرسلة

```json
{
  "customerName": "Ahmed Mohamed",
  "phoneNumber": "01000000000",
  "address": "Cairo",
  "notes": "No onions",
  "items": [
    {
      "mealId": 1,
      "quantity": 2
    },
    {
      "mealId": 3,
      "quantity": 1
    }
  ]
}
```

---

# نماذج البيانات (Shared Models)

## Meal

| الحقل | النوع | الوصف |
|--------|--------|--------|
| id | Integer | رقم الوجبة |
| name | String | اسم الوجبة |
| description | String | وصف الوجبة |
| price | Decimal | السعر |
| imageUrl | String | صورة الوجبة |
| categoryId | Integer | رقم التصنيف |

---

## Category

| الحقل | النوع | الوصف |
|--------|--------|--------|
| id | Integer | رقم التصنيف |
| name | String | اسم التصنيف |

---

## Customer Order

| الحقل | النوع | الوصف |
|--------|--------|--------|
| customerName | String | اسم العميل |
| phoneNumber | String | رقم الهاتف |
| address | String | العنوان |
| notes | String | ملاحظات |

---

## Order Item

| الحقل | النوع | الوصف |
|--------|--------|--------|
| mealId | Integer | رقم الوجبة |
| quantity | Integer | الكمية |

---

# قواعد العمل

- يلتزم Frontend و Backend بنفس أسماء الحقول.
- يمنع تغيير أسماء الحقول أثناء التطوير دون الرجوع للفريق.
- أي Endpoint جديد يجب إضافته إلى هذه الوثيقة قبل تنفيذه.
- جميع البيانات المتبادلة تكون بصيغة JSON.

---

# ملاحظات

هذه الوثيقة تمثل المرجع الرسمي لشكل البيانات داخل المشروع.

أي عضو جديد ينضم للفريق يجب أن يراجع هذه الوثيقة قبل البدء في البرمجة.

---

**إصدار الوثيقة:** v1.0

**آخر تحديث:** يوليو 2026

**إعداد:** فريق المشروع