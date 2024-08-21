
# Project Interface
```typescript
interface IProject {
  name: string
  id: string
  budget: number
  category: 'simple'|'phases'|'phase'
  city: string|null
  country: string|null
  databases_ids: {
    workers: string
    suppliers: string
    contractors: string
    apus: string
  }
}
```

# List Projects

| -Key-| -Value- |
|-----------|----------|
| **Method** | **GET** |
| **Path** | https://us-central1-copres-firebase.cloudfunctions.net/app-api/projects/|
| **Content-Type**   | application/json |
| **Authorization**   | Bearer YOUR_TOKEN_HERE |



## Response
```typescript
interface Response {
  projects: IProject[]
}
```

# Get Project

| -Key-| -Value- |
|-----------|----------|
| **Method** | **GET** |
| **Path** | https://us-central1-copres-firebase.cloudfunctions.net/app-api/projects//PROJECT_ID|
| **Content-Type**   | application/json |
| **Authorization**   | Bearer YOUR_TOKEN_HERE |



## Response
```typescript
interface Response {
  project: IProject
}
```