# Supplier Management API Documentation

## ISupplierRelation Interface
```typescript
interface ISupplierRelation {
  id: string;
  is_from_data_base: boolean;
  updatedAt: Date;
  createdAt: Date;
  supplier_data: {
    email: string | null;
    name: string;
    account_id: string | null;
    id: string | null;
  };
  user_data: {
    account_id: string;
    email: string;
    id: string;
    name: string;
  };
}
```

## List Supplier Relations

| -Key-           | -Value-                                       |
|-----------------|-----------------------------------------------|
| **Method**      | **GET**                                       |
| **Path**        | `https://us-central1-copres-firebase.cloudfunctions.net/app-api/suppliers`                              |
| **Content-Type**| `application/json`                            |
| **Authorization**| `Bearer YOUR_TOKEN_HERE`                     |

### Response
```typescript
interface Response {
  suppliers_relations: ISupplierRelation[];
}
```

## Get Supplier Relation

| -Key-           | -Value-                                       |
|-----------------|-----------------------------------------------|
| **Method**      | **GET**                                       |
| **Path**        | `https://us-central1-copres-firebase.cloudfunctions.net/app-api/suppliers/:id`                          |
| **Content-Type**| `application/json`                            |
| **Authorization**| `Bearer YOUR_TOKEN_HERE`                     |

### Response
```typescript
interface Response {
  supplier_relation: ISupplierRelation;
}
```

## ISupplierDocumentCategory Interface
```typescript
interface ISupplierDocumentCategory {
  name: string; // UPPER CASE AND SEPARATED BY spaces
  code: string; // LOWER CASE AND SEPARATED BY underscores
}
```

## ISupplierDocumentType Union
```typescript
type ISupplierDocumentType = 
  | { name: "Contract Record"; code: "contract_record" }
  | { name: "Invoice"; code: "invoice" }
  | { name: "Payroll Period"; code: "payroll_period" };
```

## ISupplierDocument Interface
```typescript
interface ISupplierDocument {
  id: string;
  type: ISupplierDocumentType;
  date: Date;
  code: string;
  createdAt: Date;
  consecutive: number;
  customer: {
    id: string | null;
    name: string;
  };
  platform: string;
  project_id: string;
  cost_center: string;
  category: ISupplierDocumentCategory;
  sub_total_value: number;
  tax: number;
}
```

## List Documents for a Supplier Relation

| -Key-           | -Value-                                       |
|-----------------|-----------------------------------------------|
| **Method**      | **GET**                                       |
| **Path**        | `https://us-central1-copres-firebase.cloudfunctions.net/app-api/suppliers/:id/documents/`               |
| **Content-Type**| `application/json`                            |
| **Authorization**| `Bearer YOUR_TOKEN_HERE`                     |

### Response
```typescript
interface Response {
  documents: ISupplierDocument[];
}
```

## Get a Specific Document

| -Key-           | -Value-                                       |
|-----------------|-----------------------------------------------|
| **Method**      | **GET**                                       |
| **Path**        | `https://us-central1-copres-firebase.cloudfunctions.net/app-api/suppliers/:id/documents/:document_id`   |
| **Content-Type**| `application/json`                            |
| **Authorization**| `Bearer YOUR_TOKEN_HERE`                     |

### Response
```typescript
interface Response {
  document: ISupplierDocument;
}
```

## Create a Supplier Document

| -Key-           | -Value-                                       |
|-----------------|-----------------------------------------------|
| **Method**      | **POST**                                      |
| **Path**        | `https://us-central1-copres-firebase.cloudfunctions.net/app-api/suppliers/:id/documents/`               |
| **Content-Type**| `application/json`                            |
| **Authorization**| `Bearer YOUR_TOKEN_HERE`                     |

### Request Body
```typescript
interface CreateDocumentRequest {
  document: {
    type: ISupplierDocumentType;
    project_id: string;
    cost_center: string;
    category_code: string;
    sub_total_value: number;
    tax: number;
  };
}
```

### Response
```typescript
interface Response {
  document: ISupplierDocument;
}
```

## IAssignedProject Interface
```typescript
interface IAssignedProject {
  category: 'Fase' | 'Fases' | 'Presupuesto';
  city: string;
  country: string;
  id: string;
  name: string;
  parent: string | null;
  tax: string | null;
}
```

## List Assigned Projects for a Supplier Relation

| -Key-           | -Value-                                       |
|-----------------|-----------------------------------------------|
| **Method**      | **GET**                                       |
| **Path**        | `https://us-central1-copres-firebase.cloudfunctions.net/app-api/suppliers/:id/assigned_projects/`       |
| **Content-Type**| `application/json`                            |
| **Authorization**| `Bearer YOUR_TOKEN_HERE`                     |

### Response
```typescript
interface Response {
  assigned_projects: IAssignedProject[];
}
```
