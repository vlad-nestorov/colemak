# Custom Colemak
This is based on the [official Colemak mapping](https://colemak.com/Windows)
Customizations (TODO):
- [x] remove `ctrl-alt`, `ctrl-alt-shift` mappings
- [x] remap modifier keys

## Building
Use [Microsoft Keyboard Layout Creator (MSKLC)](https://www.microsoft.com/en-us/download/details.aspx?id=102134)

## Remapping modifier keys
Modify `kdb.h` in MSKLC install folder (ex `C:\Program Files (x86)\Microsoft Keyboard Layout Creator 1.4\inc\kbd.h`)

The below patch remaps these keys:
```
LCTRL -> LWIN
LWIN  -> LALT
LALT  -> LCTRL
```
```
@@ -1062 +1062 @@ typedef struct tagKBD_TYPE_INFO {
-#define T1D _EQ(                           LCONTROL                  )
+#define T1D _EQ(                           LWIN                      )

@@ -1089 +1089 @@ typedef struct tagKBD_TYPE_INFO {
-#define T38 _EQ(                           LMENU                     )
+#define T38 _EQ(                           LCONTROL                  )

@@ -1187 +1187 @@ typedef struct tagKBD_TYPE_INFO {
-#define X5B _EQ(                           LWIN                      )
+#define X5B _EQ(                           LMENU                     )

@@ -2144,2 +2144,2 @@ typedef struct tagKBD_TYPE_INFO {
-#define SCANCODE_CTRL        0x1D
-#define SCANCODE_ALT         0x38
+#define SCANCODE_CTRL        0x38
+#define SCANCODE_ALT         0x5B

@@ -2151 +2151 @@ typedef struct tagKBD_TYPE_INFO {
-#define SCANCODE_LWIN         0x5B
+#define SCANCODE_LWIN         0x1D
```