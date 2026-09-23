## Connect NestJS with Prisma and Supabase (Prisma v8)

#### Create Project
```bash
nest new my-nest
```
```bash
cd my-nest
```
---

### install @nestjs/config
```bash
npm i @nestjs/config
```

### `app.module.ts`
```bash
import { Module } from '@nestjs/common';
import { AppController } from './app.controller';
import { AppService } from './app.service';
import { ConfigModule } from '@nestjs/config';

@Module({
  imports: [ConfigModule.forRoot({ isGlobal: true })],
  controllers: [AppController],
  providers: [AppService],
})
export class AppModule {}
```

>#### Direct connection string theke Session pooler select koro.
<img width="752" height="621" alt="image" src="https://github.com/user-attachments/assets/731491a3-a490-42c6-83f1-a8c912af7244" />

>#### Connection string er url copy koro.
<img width="726" height="351" alt="image" src="https://github.com/user-attachments/assets/ebd1fee8-338e-4dab-ad13-4fde7699eb0d" />


#### `.env.example`
```bash
DATABASE_URL=""
```
---


#### Prisma v8 install
```bash
npm install -D prisma@latest
```
```bash
npm install @prisma/orm-postgres
```
> interactive setup
```bash
npx prisma@latest orm init --target postgres
```
> Or, non-interactive setup  [recommended]
```bash
npx prisma@latest orm init --yes --target postgres --authoring psl
```
---


>#### example.env theke DATABASE_URL copy kore .env te paste koro.
#### `.env`
```bash
DATABASE_URL=""
```
---


#### `contract.prisma`
```bash
model Book {
  id String @id @default(uuid())
  title String
  author String
  createdAt DateTime @default(now())
}
```
---


>#### Prisma 8 Database Initialization
>- Initialize Database
```bash
npx prisma@latest contract emit
```
```bash
npx prisma db init
```
```bash
npx prisma@latest db verify
```
>- Existing Database
```bash
npx prisma@latest contract emit
```
```bash
npx prisma@latest db update --dry-run
```
```bash
npx prisma db update
```
```bash
npx prisma@latest db verify
```
<img width="1294" height="322" alt="image" src="https://github.com/user-attachments/assets/080b61fb-a379-4ca3-b64a-64972e6290de" />

---
