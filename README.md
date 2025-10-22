# `common_utils` Module

## 📘 Purpose
The **`common_utils`** module provides a collection of reusable utility services and access checks designed for use across the application—particularly with the **Group module**.  

It includes:
- Access control mechanisms  
- User-related functionality  
- Moderation logging utilities  

---

## 📂 File Structure
```
web/modules/custom/common_utils
├── src
│   ├── Access
│   │   ├── AccessCheck.php
│   │   ├── EvaluationCheck.php
│   │   └── ModeratorCheck.php
│   ├── Controller
│   │   └── LoginController.php
│   ├── Option
│   │   ├── FieldOption.php
│   │   └── GroupOption.php
│   ├── Plugin
│   │   ├── Block
│   │   │   ├── HorizontalLineBlock.php
│   │   │   └── ModerationFooterInfoBlock.php
│   │   └── Option
│   │       └── DropdownOption.php
│   ├── Service
│   │   └── ModerationLog.php
│   └── User
│       └── User.php
├── common_utils.info.yml
├── common_utils.routing.yml
└── common_utils.services.yml
```

---

## ⚙️ Services

### 1. `pennchas_common.access_check`
- **Class:** `\Drupal\common_utils\Access\AccessCheck`  
- **Arguments:** `@current_user`  
- **Purpose:**  
  Verifies if the current user possesses a specific permission at either the group (house) level or the global Drupal level.

---

### 2. `pennchas_common.moderator_access_check`
- **Class:** `\Drupal\common_utils\Access\ModeratorCheck`  
- **Arguments:** `@current_user`  
- **Purpose:**  
  Determines whether the currently logged-in user is authorized to moderate a given node.

---

### 3. `pennchas_common.evaluation_check`
- **Class:** `\Drupal\common_utils\Access\EvaluationCheck`  
- **Arguments:** `@current_user`  
- **Purpose:**  
  Checks whether the current user is permitted to evaluate a specific node.

---

### 4. `pennchas_common.option_group`
- **Class:** `\Drupal\common_utils\Option\GroupOption`  
- **Arguments:** `@current_user`  
- **Purpose:**  
  Retrieves a list of houses, either all available or only those accessible to the logged-in user.

---

### 5. `pennchas_common.field_values_label`
- **Class:** `\Drupal\common_utils\Option\FieldOption`  
- **Purpose:**  
  Provides methods to retrieve human-readable labels for selected field values and a list of allowed value labels.  
  *(Designed for “List” type entity fields.)*

---

### 6. `pennchas_common.users`
- **Class:** `\Drupal\common_utils\User\User`  
- **Purpose:**  
  Retrieves a list of user IDs that hold a specified permission.  
  The list may include:
  - Drupal users  
  - Group/house users  
  - Or both  

---

### 7. `pennchas_common.moderation_log`
- **Class:** `\Drupal\common_utils\Service\ModerationLog`  
- **Arguments:** `@database`, `@date.formatter`, `@renderer`  
- **Purpose:**  
  Generates an HTML-rendered table displaying moderation flow data for a given node ID (for nodes that support moderation).

---

## 🧩 Usage
The **`common_utils`** module serves as a **centralized custom Drupal utility module** that consolidates reusable helper logic, services, and configurations shared across multiple custom modules within the **PennCHAS site**.
