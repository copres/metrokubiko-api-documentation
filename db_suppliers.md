
# Supplier Interface
```typescript
export interface ISupplier {
  id: string
  city: string
  code: string
  direction: string
  email: string
  is_niple_supplier: boolean
  id_value: string
  id_type: string
  name: string
  parent: string
  product: string
  phone: string
  createdAt: Date
  updatedAt: Date
}

export interface ISupplierDB {
  id: string
  name: string
  city: string
  country: string
  active: boolean
}

```

# List Suppliers

| -Key-| -Value- |
|-----------|----------|
| **Method** | **GET** |
| **Path** | https://us-central1-copres-firebase.cloudfunctions.net/app-api/db_suppliers/:db_id/suppliers|
| **Content-Type**   | application/json |
| **Authorization**   | Bearer YOUR_TOKEN_HERE |



## Response
```typescript
interface Response {
  suppliers: ISupplier[]
}
```

# Get Supplier

| -Key-| -Value- |
|-----------|----------|
| **Method** | **GET** |
| **Path** | https://us-central1-copres-firebase.cloudfunctions.net/app-api/db_suppliers/:db_id/suppliers/:supplier_id|
| **Content-Type**   | application/json |
| **Authorization**   | Bearer YOUR_TOKEN_HERE |



## Response
```typescript
interface Response {
  supplier: ISupplier
}
```

# List Suppliers DBs

| -Key-| -Value- |
|-----------|----------|
| **Method** | **GET** |
| **Path** | https://us-central1-copres-firebase.cloudfunctions.net/app-api/db_suppliers/|
| **Content-Type**   | application/json |
| **Authorization**   | Bearer YOUR_TOKEN_HERE |



## Response
```typescript
interface Response {
  suppliers_dbs: ISupplierDB[]
}
```

# Get Suppliers DB

| -Key-| -Value- |
|-----------|----------|
| **Method** | **GET** |
| **Path** | https://us-central1-copres-firebase.cloudfunctions.net/app-api/db_suppliers/:db_id|
| **Content-Type**   | application/json |
| **Authorization**   | Bearer YOUR_TOKEN_HERE |



## Response
```typescript
interface Response {
  supplier_db: ISupplierDB
}
```
