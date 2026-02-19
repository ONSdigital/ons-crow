
# CROW Cluster Version Instructions

> **Note:** All exemplar data displayed in this document is fake, synthetic data.

---
## Input File Requirements
- Files must be **CSV** files.
- They must be **long format** (one row per record). A cluster will contain multiple rows.
- There must be a **cluster ID** column (any unique string per cluster).
- There must be a **record ID** column (unique for each record).

Example input format:
![image_0_Image23.png](ons-crow/version1_tkinter/docs/images/image_0_Image23.png)

---
## Setting Up the Config File (for project leads)

### `[column_headers_and_order]`
Specify the text you want to appear as the header for each row.

### `[column_file_info_and_order]`
Specify how CROW reads the variables in your CSV.

### `[cluster_id]`
Specify the cluster ID column.

### `[record_id]`
Specify the record ID column.
![image_1_Image26.png](ons-crow/version1_tkinter/docs/images/image_1_Image26.png)

---
## Custom Settings
- **commentbox** toggle
- **comment_values** dropdown examples
![image_1_Image27.png](ons-crow/version1_tkinter/docs/images/image_1_Image27.png)

---
## Using the Cluster Review Version
Run the Python editor.
![image_1_Image28.png](ons-crow/version1_tkinter/docs/images/image_1_Image28.png)

After selecting a file:
![image_2_Image31.png](ons-crow/version1_tkinter/docs/images/image_2_Image31.png)
![image_2_Image32.png](ons-crow/version1_tkinter/docs/images/image_2_Image32.png)

---
## The Output
A Match column is appended.
![image_3_Image35.png](ons-crow/version1_tkinter/docs/images/image_3_Image35.png)

To produce pairwise format, run:
```
CROW_output_updater.py
```
