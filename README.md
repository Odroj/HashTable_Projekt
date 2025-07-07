# 🗂️ Hash Table in C

A robust and dynamic hash table implementation written in C, designed to efficiently store and manage key–value pairs. This project showcases techniques such as open addressing, double hashing, dynamic memory allocation, and prime-based resizing to optimize lookup and insertion operations.

---

## 🔧 Features

- **Hash Table Data Structure**  
  Implements a custom `ht_hash_table` capable of storing string-based key–value pairs efficiently.

- **Open Addressing with Double Hashing**  
  Resolves collisions by probing alternate indices, ensuring uniform distribution and minimal clustering.

- **Upsert Logic**  
  Automatically updates existing keys with new values, enabling cleaner state management.

- **Dynamic Resizing**  
  The table grows or shrinks based on load factor, using prime number sizing to maintain hashing efficiency.

- **Prime Number Validation**  
  Includes `is_prime()` logic to find the next valid size when resizing.

- **Deletion and Tombstones**  
  Supports safe deletion via `HT_DELETED_ITEM`, preserving probing integrity for subsequent searches and inserts.

---

## 🧠 Techniques Used

| Technique                    | Description                                                                 |
|-----------------------------|-----------------------------------------------------------------------------|
| **Memory Management**       | Manual allocation and freeing of memory using `malloc` and custom cleanup. |
| **Hashing Functions**       | Primary and secondary hashing for key distribution and collision resolution.|
| **Double Hashing**          | Reduces clustering more effectively than linear probing alone.              |
| **Upsert Pattern**          | Inserts or updates an item based on key presence.                          |
| **Prime-Based Resizing**    | Ensures better key spread and full space utilization.                      |
| **Modular API Design**      | Functions are cleanly separated for insertion, search, and deletion.       |

---

## 📦 Functions Exposed

```c
void ht_insert(ht_hash_table* ht, const char* key, const char* value);
char* ht_search(ht_hash_table* ht, const char* key);
void ht_delete(ht_hash_table* ht, const char* key);
