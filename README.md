# 🍽️ Restaurant POS System  

A full-featured **Restaurant Point of Sale (POS)** system built with **NestJS (Backend)**, **Next.js (Frontend)**, and **PostgreSQL (Database)**.  
The system supports **staff management, table management, menu & orders, billing & payments, kitchen display system (KDS), inventory, analytics, and advanced features** like QR code ordering, loyalty programs, and hotel integration.  

---

## 🚀 Tech Stack
- **Backend**: NestJS + PostgreSQL (TypeORM / Prisma / Sequelize)  
- **Frontend**: Next.js (React, TypeScript)  
- **Real-time**: WebSockets / Socket.IO  
- **Authentication**: JWT + RBAC (Role-Based Access Control)  

---

## 📐 Project Architecture

### Backend (NestJS + PostgreSQL)
**Modules:**
- `Auth` → JWT, Roles, Permissions  
- `User` → Staff Management (Admin, Waiter, Cashier, Kitchen Staff)  
- `Table` → Table CRUD, Reservations  
- `Menu` → Products, Categories, Combos, Add-ons  
- `Order` → Dine-in, Takeaway, Delivery Orders  
- `Payment` → Billing, Taxes, Discounts, Receipts  
- `Kitchen` → KDS, Order Tracking  
- `Inventory` → Stock, Ingredients, Purchases  
- `Report` → Sales, Analytics  
- `Hotel` → (Optional Plugin for Hotel Integration)  

### Frontend (Next.js)
**Interfaces:**
- **Admin Panel**  
  - Dashboard (sales, performance)  
  - Staff Management  
  - Menu & Inventory  
  - Reports & Analytics  

- **POS Interface**  
  - Table Grid View  
  - Order Screen (add items, assign waiter)  
  - Payment Screen  
  - Reservation Screen  
  - Kitchen Display (KDS)  
  - Customer Self-Ordering (QR code menu)  

---

## 📋 Features

### 👨‍🍳 Staff & User Management
- Roles: **Admin, Waiter, Cashier, Kitchen Staff, Manager**  
- CRUD for staff accounts  
- Assign waiters to tables & kitchen staff to order types  
- Attendance & shift management (optional)  

### 🍽️ Table Management
- Create/manage tables (number, capacity, zone)  
- Table statuses: **Available, Occupied, Reserved, Dirty**  
- Assign waiter → table  
- Reservation system (customer name, phone, time)  
- Auto-clean/free table after order completion  

### 🧾 Menu & Product Management
- Categories (Appetizers, Drinks, Main Course, etc.)  
- Products (name, price, cost, description, image, availability)  
- Combo Meals / Packages / Set Menus  
- Add-ons & Modifiers (extra cheese, toppings)  
- Pricing rules (happy hour discounts, promotions)  

### 📦 Order Management
- Create/Update Orders  
- Transfer & Split Orders  
- Kitchen Order Ticket (KOT) auto-sent to kitchen  
- Order Types: **Dine-in, Takeaway, Delivery**  

### 💳 Billing & Payments
- Multiple payment methods: Cash, Card, Mobile Wallet  
- Split bill per item or person  
- Discounts, coupons, taxes, service charges  
- Generate receipts (Print/PDF/Email)  
- Refunds / Order cancellations  

### 🔥 Kitchen Management (KDS)
- Kitchen Display System (separate screen)  
- Track order status → Pending → Cooking → Ready → Served  
- Auto-routing: Drinks → Bar, Food → Kitchen  
- Notifications when order ready  

### 📦 Inventory & Stock
- Ingredients & recipe-based stock deduction  
- Purchase management (suppliers, invoices)  
- Low stock alerts  
- Wastage/returns tracking  

### 🛎️ Front Desk / Reservations
- Customer reservations (walk-in, phone, online)  
- Table allocation & queue management  
- Customer preferences (VIP, allergies, notes)  

### 📊 Reports & Analytics
- Daily, weekly, monthly sales  
- Waiter & kitchen performance  
- Table utilization  
- Inventory usage/wastage  
- Profit & loss, best-selling items  

### 🔗 Advanced Features
- QR Code Ordering (scan table QR → order directly)  
- Loyalty Program (points, discounts)  
- Multi-branch Management  
- Offline Mode (cache orders, sync when online)  
- Mobile App for Waiters (tablet/phone ordering)  
- Hotel Integration (room → table/order, sync bills)  

---

## 🛠️ Development Roadmap

### 📍 Phase 1: Foundation (Core Setup)
- ✅ Setup NestJS + PostgreSQL  
- ✅ Setup Next.js frontend  
- ✅ Auth & RBAC with JWT + Refresh Token  
- ✅ Basic Admin Dashboard  

### 📍 Phase 2: Staff & Table Management
- Staff CRUD & role assignment  
- Table CRUD + statuses (Available, Reserved, Dirty, Occupied)  
- Reservation system  

### 📍 Phase 3: Menu & Product Management
- Categories & products CRUD  
- Add-ons, modifiers, combo meals  
- POS menu display  

### 📍 Phase 4: Order Management
- Order creation & update  
- Split/transfer orders  
- Kitchen Order Tickets (KOT)  

### 📍 Phase 5: Kitchen Management (KDS)
- Kitchen display screen  
- Order status flow (Pending → Cooking → Ready → Served)  

### 📍 Phase 6: Billing & Payments
- Taxes, service charges, discounts  
- Multiple payment methods  
- Split bills, receipts, refunds  

### 📍 Phase 7: Inventory & Stock
- Recipe-based stock deduction  
- Supplier management  
- Low stock alerts, wastage tracking  

### 📍 Phase 8: Reports & Analytics
- Sales, staff performance, table utilization  
- Inventory usage & wastage  
- Profit & loss reports  

### 📍 Phase 9: Advanced Features
- QR ordering, loyalty, multi-branch  
- Offline mode, mobile apps  
- Hotel integration  

 

## 🍽️ NestJS project structure with modules

```lua
/restaurant-pos
 ├── src
 │   ├── app.module.ts
 │   ├── main.ts
 │   │
 │   ├── modules
 │   │    ├── tables
 │   │    │    ├── tables.module.ts
 │   │    │    ├── tables.controller.ts
 │   │    │    ├── tables.service.ts
 │   │    │    └── entities/table.entity.ts
 │   │    │
 │   │    ├── waiters
 │   │    │    ├── waiters.module.ts
 │   │    │    ├── waiters.controller.ts
 │   │    │    ├── waiters.service.ts
 │   │    │    └── entities/waiter.entity.ts
 │   │    │
 │   │    ├── menu
 │   │    │    ├── menu.module.ts
 │   │    │    ├── menu.controller.ts
 │   │    │    ├── menu.service.ts
 │   │    │    └── entities/menu-item.entity.ts
 │   │    │
 │   │    ├── orders
 │   │    │    ├── orders.module.ts
 │   │    │    ├── orders.controller.ts
 │   │    │    ├── orders.service.ts
 │   │    │    └── entities/order.entity.ts
 │   │    │
 │   │    ├── packages
 │   │    │    ├── packages.module.ts
 │   │    │    ├── packages.controller.ts
 │   │    │    ├── packages.service.ts
 │   │    │    └── entities/package.entity.ts
 │   │    │
 │   │    ├── reservations   # Hotel reservation plugin
 │   │    │    ├── reservations.module.ts
 │   │    │    ├── reservations.controller.ts
 │   │    │    ├── reservations.service.ts
 │   │    │    └── entities/reservation.entity.ts
 │   │    │
 │   │    ├── kitchen
 │   │    │    ├── kitchen.module.ts
 │   │    │    ├── kitchen.controller.ts
 │   │    │    ├── kitchen.service.ts
 │   │    │    └── entities/kitchen.entity.ts
 │   │    │
 │   │    ├── frontdesk
 │   │    │    ├── frontdesk.module.ts
 │   │    │    ├── frontdesk.controller.ts
 │   │    │    ├── frontdesk.service.ts
 │   │    │    └── entities/frontdesk.entity.ts
 │   │
 │   ├── common   # shared utils, DTOs, decorators
 │   │    ├── dto
 │   │    ├── guards
 │   │    └── interceptors
 │   │
 │   └── config
 │        └── typeorm.config.ts
 │
 ├── package.json
 ├── tsconfig.json
 └── nest-cli.json

```

## 🍽️ Restaurant POS – Database Schema (ERD)

   __1. User & Roles__

```markdown
    ## roles

    id (PK)
    name (Admin, Waiter, Cashier, Kitchen, Manager)

    ## users

    id (PK)
    name
    email
    password
    role_id (FK → roles.id)
    status (active/inactive)
    created_at
    updated_at
```

   __2. Table Management _-

```markdown
    tables
    ---------
    id (PK)
    table_number (unique)
    capacity
    zone (e.g., Hall A, Rooftop)
    status (available, occupied, reserved, dirty)
    current_order_id (FK → orders.id, nullable)
    created_at
    updated_at

    reservations
    ---------
    id (PK)
    table_id (FK → tables.id)
    customer_name
    customer_phone
    reservation_time
    status (reserved, cancelled, completed)
    created_at
    updated_at
```

   __3. Menu & Products__

```markdown
    categories
    ---------
    id (PK)
    name
    description
    created_at
    updated_at

    products
    ---------
    id (PK)
    category_id (FK → categories.id)
    name
    description
    price
    cost_price
    is_available (boolean)
    image_url
    created_at
    updated_at

    product_modifiers
    ---------
    id (PK)
    product_id (FK → products.id)
    name (e.g., Extra Cheese)
    price
    created_at
    updated_at

    packages (for combo/set meals)
    ---------
    id (PK)
    name
    description
    price
    created_at
    updated_at

    package_items
    ---------
    id (PK)
    package_id (FK → packages.id)
    product_id (FK → products.id)
    quantity
```

   __4. Orders__

```markdown
    orders
    ---------
    id (PK)
    table_id (FK → tables.id, nullable for takeaway/delivery)
    waiter_id (FK → users.id)
    status (pending, cooking, ready, served, paid, cancelled)
    order_type (dine-in, takeaway, delivery)
    created_at
    updated_at

    order_items
    ---------
    id (PK)
    order_id (FK → orders.id)
    product_id (FK → products.id)
    quantity
    price
    modifier_ids (JSON array → [1,2,3])
    status (pending, cooking, ready, served)
```

   __5. Payments__

```markdown
    payments
    ---------
    id (PK)
    order_id (FK → orders.id)
    amount
    payment_method (cash, card, wallet)
    status (paid, refunded, partial)
    transaction_id (optional)
    created_at
    updated_at

    bills
    ---------
    id (PK)
    order_id (FK → orders.id)
    subtotal
    tax
    service_charge
    discount
    total
    created_at
    updated_at
```

   __6. Kitchen Management__

```markdown
    kitchen_orders
    ---------
    id (PK)
    order_item_id (FK → order_items.id)
    status (pending, cooking, ready, served)
    assigned_to (FK → users.id → kitchen staff, nullable)
    started_at
    finished_at
```

   ___7. Inventory & Stock__

```markdown
    ingredients
    ---------
    id (PK)
    name
    unit (kg, liter, pcs)
    stock_quantity
    reorder_level
    created_at
    updated_at

    recipes
    ---------
    id (PK)
    product_id (FK → products.id)
    ingredient_id (FK → ingredients.id)
    quantity_used

    purchases
    ---------
    id (PK)
    supplier_name
    invoice_number
    total_amount
    created_at
    updated_at

    purchase_items
    ---------
    id (PK)
    purchase_id (FK → purchases.id)
    ingredient_id (FK → ingredients.id)
    quantity
    unit_price
```

    ## 🔗 Key Relationships
        - One Role → Many Users
        - One Table → Many Reservations
        - One Category → Many Products
        - One Product → Many Order Items
        - One Order → Many Order Items & One Bill
        - One Order Item → One Kitchen Order
        - One Product → Many Ingredients (via recipes)
        - One Purchase → Many Purchase Items


    ## ✅ ERD Flow
       - Users (Staff) → Manage Tables + Reservations
       - Tables → Link with Orders
       - Orders → Have Order Items → Linked to Products
       - Products → Linked to Recipes → Reduce Ingredients (Inventory)
       - Orders → Linked to Bills & Payments
       - Kitchen Orders → Track order status



    ## NestJS TypeORM entity structure

```ts
import {
  Entity,
  PrimaryGeneratedColumn,
  Column,
  ManyToOne,
  OneToMany,
  JoinColumn,
} from "typeorm";

// ------------------------- Company -------------------------
@Entity("companies")
export class Company {
  @PrimaryGeneratedColumn()
  id: number;

  @Column()
  name: string;

  @OneToMany(() => Branch, (branch) => branch.company)
  branches: Branch[];
}

// ------------------------- Branch -------------------------
@Entity("branches")
export class Branch {
  @PrimaryGeneratedColumn()
  id: number;

  @Column()
  name: string;

  @ManyToOne(() => Company, (company) => company.branches)
  @JoinColumn({ name: "company_id" })
  company: Company;

  @OneToMany(() => TableEntity, (table) => table.branch)
  tables: TableEntity[];
}

// ------------------------- Table -------------------------
@Entity("tables")
export class TableEntity {
  @PrimaryGeneratedColumn()
  id: number;

  @Column()
  table_number: string;

  @Column()
  capacity: number;

  @ManyToOne(() => Branch, (branch) => branch.tables)
  @JoinColumn({ name: "branch_id" })
  branch: Branch;

  @OneToMany(() => Reservation, (reservation) => reservation.table)
  reservations: Reservation[];

  @OneToMany(() => Order, (order) => order.table)
  orders: Order[];
}

// ------------------------- Reservation -------------------------
@Entity("reservations")
export class Reservation {
  @PrimaryGeneratedColumn()
  id: number;

  @Column()
  customer_name: string;

  @Column()
  customer_phone: string;

  @Column({ type: "timestamp" })
  reservation_time: Date;

  @ManyToOne(() => TableEntity, (table) => table.reservations)
  @JoinColumn({ name: "table_id" })
  table: TableEntity;
}

// ------------------------- Category -------------------------
@Entity("categories")
export class Category {
  @PrimaryGeneratedColumn()
  id: number;

  @Column()
  name: string;

  @OneToMany(() => Product, (product) => product.category)
  products: Product[];
}

// ------------------------- Product -------------------------
@Entity("products")
export class Product {
  @PrimaryGeneratedColumn()
  id: number;

  @Column()
  name: string;

  @Column("decimal", { precision: 10, scale: 2 })
  price: number;

  @ManyToOne(() => Category, (category) => category.products)
  @JoinColumn({ name: "category_id" })
  category: Category;

  @OneToMany(() => OrderItem, (orderItem) => orderItem.product)
  orderItems: OrderItem[];
}

// ------------------------- Order -------------------------
@Entity("orders")
export class Order {
  @PrimaryGeneratedColumn()
  id: number;

  @Column({ type: "timestamp", default: () => "CURRENT_TIMESTAMP" })
  order_time: Date;

  @ManyToOne(() => TableEntity, (table) => table.orders)
  @JoinColumn({ name: "table_id" })
  table: TableEntity;

  @OneToMany(() => OrderItem, (orderItem) => orderItem.order)
  items: OrderItem[];

  @OneToMany(() => Payment, (payment) => payment.order)
  payments: Payment[];
}

// ------------------------- Order Item -------------------------
@Entity("order_items")
export class OrderItem {
  @PrimaryGeneratedColumn()
  id: number;

  @ManyToOne(() => Order, (order) => order.items)
  @JoinColumn({ name: "order_id" })
  order: Order;

  @ManyToOne(() => Product, (product) => product.orderItems)
  @JoinColumn({ name: "product_id" })
  product: Product;

  @Column("int")
  quantity: number;

  @Column("decimal", { precision: 10, scale: 2 })
  price: number;
}

// ------------------------- Payment -------------------------
@Entity("payments")
export class Payment {
  @PrimaryGeneratedColumn()
  id: number;

  @ManyToOne(() => Order, (order) => order.payments)
  @JoinColumn({ name: "order_id" })
  order: Order;

  @Column("decimal", { precision: 10, scale: 2 })
  amount: number;

  @Column()
  method: string; // cash, card, etc.

  @Column({ type: "timestamp", default: () => "CURRENT_TIMESTAMP" })
  payment_time: Date;
}

// ------------------------- Employee -------------------------
@Entity("employees")
export class Employee {
  @PrimaryGeneratedColumn()
  id: number;

  @Column()
  name: string;

  @Column()
  role: string; // waiter, cashier, chef

  @Column()
  phone: string;
}

// ------------------------- Inventory -------------------------
@Entity("inventory")
export class Inventory {
  @PrimaryGeneratedColumn()
  id: number;

  @Column()
  item_name: string;

  @Column("int")
  quantity: number;

  @Column("varchar")
  unit: string;

  @Column({ type: "timestamp", default: () => "CURRENT_TIMESTAMP" })
  updated_at: Date;
}
```

    ## Tables Module Example

```ts
// ==================== entities/table.entity.ts ====================
import { Entity, PrimaryGeneratedColumn, Column, OneToMany } from "typeorm";
import { Reservation } from "../../reservations/entities/reservation.entity";
import { Order } from "../../orders/entities/order.entity";

@Entity("tables")
export class TableEntity {
  @PrimaryGeneratedColumn()
  id: number;

  @Column({ unique: true })
  table_number: string;

  @Column("int")
  capacity: number;

  @Column({ default: "available" })
  status: string;

  @OneToMany(() => Reservation, (reservation) => reservation.table)
  reservations: Reservation[];

  @OneToMany(() => Order, (order) => order.table)
  orders: Order[];
}

// ==================== dto/create-table.dto.ts ====================
export class CreateTableDto {
  table_number: string;
  capacity: number;
  status?: string;
}

// ==================== dto/update-table.dto.ts ====================
export class UpdateTableDto {
  table_number?: string;
  capacity?: number;
  status?: string;
}

// ==================== tables.service.ts ====================
import { Injectable, NotFoundException } from "@nestjs/common";
import { InjectRepository } from "@nestjs/typeorm";
import { Repository } from "typeorm";
import { TableEntity } from "./entities/table.entity";
import { CreateTableDto } from "./dto/create-table.dto";
import { UpdateTableDto } from "./dto/update-table.dto";

@Injectable()
export class TablesService {
  constructor(
    @InjectRepository(TableEntity)
    private tableRepository: Repository<TableEntity>
  ) {}

  create(createTableDto: CreateTableDto) {
    const table = this.tableRepository.create(createTableDto);
    return this.tableRepository.save(table);
  }

  findAll() {
    return this.tableRepository.find({ relations: ["reservations", "orders"] });
  }

  async findOne(id: number) {
    const table = await this.tableRepository.findOne({
      where: { id },
      relations: ["reservations", "orders"],
    });
    if (!table) throw new NotFoundException(`Table ${id} not found`);
    return table;
  }

  async update(id: number, updateTableDto: UpdateTableDto) {
    await this.tableRepository.update(id, updateTableDto);
    return this.findOne(id);
  }

  async remove(id: number) {
    const table = await this.findOne(id);
    return this.tableRepository.remove(table);
  }
}

// ==================== tables.controller.ts ====================
import {
  Controller,
  Get,
  Post,
  Body,
  Param,
  Put,
  Delete,
} from "@nestjs/common";
import { TablesService } from "./tables.service";
import { CreateTableDto } from "./dto/create-table.dto";
import { UpdateTableDto } from "./dto/update-table.dto";

@Controller("tables")
export class TablesController {
  constructor(private readonly tablesService: TablesService) {}

  @Post()
  create(@Body() createTableDto: CreateTableDto) {
    return this.tablesService.create(createTableDto);
  }

  @Get()
  findAll() {
    return this.tablesService.findAll();
  }

  @Get(":id")
  findOne(@Param("id") id: number) {
    return this.tablesService.findOne(id);
  }

  @Put(":id")
  update(@Param("id") id: number, @Body() updateTableDto: UpdateTableDto) {
    return this.tablesService.update(id, updateTableDto);
  }

  @Delete(":id")
  remove(@Param("id") id: number) {
    return this.tablesService.remove(id);
  }
}

// ==================== tables.module.ts ====================
import { Module } from "@nestjs/common";
import { TypeOrmModule } from "@nestjs/typeorm";
import { TablesService } from "./tables.service";
import { TablesController } from "./tables.controller";
import { TableEntity } from "./entities/table.entity";

@Module({
  imports: [TypeOrmModule.forFeature([TableEntity])],
  providers: [TablesService],
  controllers: [TablesController],
})
export class TablesModule {}
```

## 🍽️ Table Management – Task List

    __1. Database & Entity Setup__

        - Create tables entity/model in PostgreSQL with fields:
            - id (PK)
            - table_number (unique identifier, e.g., T1, T2, etc.)
            - capacity (number of seats)
            - status (available, occupied, reserved, dirty)
            - location/zone (optional: e.g., Hall A, Rooftop, etc.)
            - current_order_id (FK to orders, nullable)
            - created_at, updated_at
        - Seed initial tables (e.g., 20 tables).


###2. Backend (NestJS) – API Development

        - Create Table APIs:
            - POST /tables → Add new table
            - GET /tables → List all tables with status
            - GET /tables/:id → Get table details
            - PATCH /tables/:id → Update table info (capacity, location)
            - DELETE /tables/:id → Soft delete table (if needed)

        - Table Status Management
            - PATCH /tables/:id/status → Change table status (available, occupied, reserved, dirty)
            - Auto-update status when order is placed/closed

        - Reservation API:
            - POST /tables/:id/reserve → Reserve a table for a customer
            - PATCH /tables/:id/cancel-reservation

        - Integration with Orders:
            - When a waiter opens an order → link it to a table
            - When the order is closed → free the table

###3. Frontend (NextJS) – UI/UX

        - Table Dashboard (Grid View):
            - Show all tables in a visual grid/floor plan
            - Different colors for status:
                🟩 Available
                🟨 Reserved
                🟥 Occupied
                🟦 Dirty

        - Table Details Modal
            - Capacity, current order, waiter assigned
            - Actions: Reserve, Occupy, Free, Mark Dirty

        - Reservation Form
            - Customer name, phone number
            - Time of reservation
            - Assign waiter (optional)
            - Waiter Assignment
            - Assign waiter per table
            - Show waiter name on table card
            - Drag & Drop Floor Plan (Future Feature)
            - Allow admin to rearrange tables visually


###4. Extra Features (Advanced)

        🔄 Auto Refresh Table Status (WebSockets/Socket.io for real-time updates)
        📱 QR Code per Table → customer can scan & view menu/order
        🧹 Dirty → Clean Flow → after payment, table becomes “dirty” until cleaned
        📊 Analytics
            - Table occupancy rate
            - Average dining time
            - Most used tables/zones

###5. Task Breakdown (Project Steps)
        - DB Migration – Create tables table
        - NestJS Table Module – CRUD + status APIs
        - NextJS Table Dashboard – Grid display with status colors
        - Reservation + Waiter assignment integration
        - Order-Table linking (when new order created)
        - Real-time updates with WebSockets
        - Optional: Floor plan drag-drop + QR ordering