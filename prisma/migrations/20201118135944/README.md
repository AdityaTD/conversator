# Migration `20201118135944`

This migration has been generated by Aditya N. Tripathi at 11/18/2020, 7:29:44 PM.
You can check out the [state of the schema](./schema.prisma) after the migration.

## Database Steps

```sql
CREATE TABLE "guild" (
    "id" TEXT NOT NULL,
    "prefix" TEXT NOT NULL,
    "channel" TEXT,
    "enabled" BOOLEAN,
    PRIMARY KEY ("id")
)

CREATE UNIQUE INDEX "guild.id_unique" ON "guild"("id")
```

## Changes

```diff
diff --git schema.prisma schema.prisma
migration ..20201118135944
--- datamodel.dml
+++ datamodel.dml
@@ -1,0 +1,15 @@
+generator client {
+  provider = "prisma-client-js"
+}
+
+datasource db {
+  provider = "sqlite"
+  url = "***"
+}
+
+model guild {
+  id      String   @unique @id
+  prefix  String
+  channel String?
+  enabled Boolean?
+}
```


