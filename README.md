# Technical Foundation: Book Category Data Dictionary

This repository contains the technical specifications and implementation steps for creating a custom **Book Category** data type in the SAP ABAP Dictionary (DDIC).

## Overview

In SAP, we follow a three-tier approach to data definition:

1. **Domain:** Defines the technical attributes (Type, Length, Fixed Values).
2. **Data Element:** Adds semantic meaning (Labels, Documentation).
3. **Table Field:** Uses the Data Element to store actual records.

---

##  Components to Create

### 1. The Domain: `ZLGM_CATAGORY_083`

The domain acts as the technical "blueprint." It restricts what kind of data can be entered.

| Attribute | Value |
| --- | --- |
| **Data Type** | `CHAR` |
| **No. Characters** | `10` |
| **Output Length** | `10` |
| **Value Range** | (See Fixed Values below) |

**Fixed Values:**

* `FICT` - Fiction
* `NONF` - Non-Fiction
* `SCIFI` - Sci-Fi
* `BIO` - Biography

### 2. The Data Element: `ZLGM_CATAGORY_083`

The Data Element provides the context. While the domain says "this is a 10-char string," the Data Element says "this string represents a Book Category."

* **Domain:** `ZBOOK_CAT_DOM`
* **Field Labels:**
* **Short:** Cat.
* **Medium:** Category
* **Long:** Book Category
* **Heading:** Book Category



## Step-by-Step Implementation

### Step 1: Create the Domain

1. Go to transaction **SE11**.
2. Select the **Domain** radio button and enter `ZBOOK_CAT_DOM`. Click **Create**.
3. Enter a Short Description (e.g., "Domain for Book Categories").
4. On the **Definition** tab, set Data Type to `CHAR` and Length to `10`.
5. On the **Value Range** tab, enter the fixed values (FICT, NONF, etc.).
6. **Save** and **Activate**.

### Step 2: Create the Data Element

1. In **SE11**, select the **Data Type** radio button and enter `ZBOOK_CAT_DE`. Click **Create**.
2. Select **Data Element** in the popup.
3. In the **Elementary Type** section, enter `ZBOOK_CAT_DOM` in the Domain field.
4. Go to the **Field Label** tab and fill in the Short, Medium, and Long labels.
5. **Save** and **Activate**.


**preview**
**Domain** - <img width="1145" height="620" alt="image" src="https://github.com/user-attachments/assets/91aab456-8d8a-4e3c-b700-e5103cb72400" />

**Data Element** - <img width="1167" height="417" alt="image" src="https://github.com/user-attachments/assets/5048df12-e280-4341-b8a0-f208c7ac659f" />

**Database Table ** <img width="812" height="585" alt="image" src="https://github.com/user-attachments/assets/4009839e-97ad-4c4d-aa30-730aed10ef80" />


**Fiori Preview **

<img width="1842" height="763" alt="image" src="https://github.com/user-attachments/assets/883eedc1-6e79-45c4-8f20-f5dd753f7b4d" />
<img width="1830" height="752" alt="image" src="https://github.com/user-attachments/assets/4f480d15-98cd-490e-bb72-ec9f16674ebc" />



