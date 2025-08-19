## 📋 Restaurant POS System – Full Task List

   __1. Core Setup__
        - Project setup (NestJS backend, Next.js frontend, PostgreSQL DB)
        - Authentication & Authorization (Admin, Waiter, Cashier, Kitchen Staff)
        - Role-based Access Control (RBAC)
        - Real-time communication (WebSockets / Socket.IO for live updates)


   __2. User & Staff Management__
        - Staff Roles → Waiters, Cashiers, Kitchen Staff, Managers
        - CRUD for Users (add, update, deactivate staff)
        - Staff assignment (e.g., waiter → tables, kitchen staff → order types)
        - Attendance & shift management (optional advanced feature)

   __3. Table Management__
        - Create/manage tables (number, capacity, zone)
        - Table status → Available, Occupied, Reserved, Dirty
        - Assign waiter to a table
        - Reservation system (customer name, phone, time)
        - Link table with current order
        - Free/clean table after order completion


   __4. Menu & Product Management__
        - Categories (Appetizers, Main Course, Drinks, etc.)
        - Products (name, price, cost, description, image, availability)
        - Combo meals / Packages
        - Set menu creation
        - Add-ons & modifiers (e.g., extra cheese, no onions)
        - Pricing rules (happy hour discounts, promotions)


   __5. Order Management__

    __Create Order__
        - Select table & waiter
        - Add items (with modifiers, add-ons)

    __Update Order__
        - Add/remove items
        - Change quantity
        - Transfer table / Split order

    __Kitchen Order Tickets (KOT)__
        - Auto-send order to kitchen display/print
        - Track order status → Pending, Cooking, Ready, Served

    __Order Linking__
        - Dine-in order → table
        - Takeaway order → customer info
        - Delivery order → customer address

   __6. Billing & Payments__
        - Multiple payment methods (cash, card, mobile wallet)
        - Split bill (per person, per item)
        - Discounts & coupons
        - Service charges & taxes
        - Generate receipt (print/PDF)
        - Refunds / order cancellation handling

   __7. Kitchen Management__
        - Kitchen Display System (KDS)
        - Show pending orders with time tracking
        - Update item status (cooking → ready)
        - Auto-routing (drinks → bar, food → kitchen)
        - Notification when order ready

   __8. Inventory & Stock__
        - Ingredients & stock items
        - Stock deduction per order (recipe-based)
        - Purchase management (supplier, invoices)
        - Low stock alerts
        - Wastage/returns tracking

   __9. Front Desk / Reservations__
        - Customer reservations (walk-in, phone, online)
        - Table allocation
        - Queue management (waiting list for customers)
        - Customer preferences (VIP, allergies, notes)

   __10. Hotel Integration (Plugin Feature)__
        (If you’re adding hotel reservation system into POS)
        - Link guest room → table or order
        - Post charges to room bill
        - Hotel guest check-in/check-out sync


   __11. Reports & Analytics__
        - Daily sales report
        - Waiter performance (tips, orders served)
        - Kitchen performance (average prep time)
        - Table utilization report
        - Inventory usage & wastage
        - Profit & loss, best-selling items


   __12. Extra Features (Optional but Powerful)__
        - Customer QR code ordering (scan table QR → order directly)
        - Loyalty program (points, discounts)
        - Multi-branch management
        - Offline mode (cache orders, sync when online)
        - Mobile app for waiters (take orders on phone/tablet)
        - Admin dashboard (manage multiple branches, analytics)

## 📐 Project Architecture (Recommended)

   __Backend (NestJS + PostgreSQL)__

       __Modules:__
            - Auth (JWT, roles, permissions)
            - User (staff management)
            - Table (table CRUD & reservations)
            - Menu (products, categories, packages)
            - Order (dine-in, takeaway, delivery)
            - Payment (billing, receipts)
            - Kitchen (order tracking, status)
            - Inventory (ingredients, stock)
            - Report (sales, analytics)
            - Hotel (plugin integration if needed)

###Frontend (Next.js)

   __Admin Panel__
        Dashboard (sales, performance)
        Staff management
        Menu management
        Reports
        Inventory

   __POS Interface__
        Table grid view
        Order screen (add items, assign waiter)
        Payment screen
        Reservation screen
        Kitchen Display (separate screen for chefs)
        Customer Self-Ordering (optional QR menu frontend)

## 🚀 Restaurant POS Development Roadmap

###📍 Phase 1: Foundation (Core Setup):
        🔹 Goal: Get the backend + frontend running with authentication and basic user roles.

   __Tasks:__
        - Setup NestJS project with PostgreSQL (TypeORM/Prisma/Sequelize).
        - Setup Next.js project for frontend.
        - Configure RBAC (Role-Based Access Control) → Admin, Waiter, Cashier, Kitchen.
        - Implement authentication (JWT + Refresh Token).
        - Build simple Admin Dashboard Layout in Next.js.
    ✅ Deliverable: You can log in as Admin/Waiter/Cashier and see different dashboards.



###📍 Phase 2: Staff & Table Management
        🔹 Goal: Manage staff and tables.

       __Tasks:__
            - Staff Management (CRUD for users, assign roles).
            - Table Management
                - CRUD for tables (number, capacity, zone).
                - Table statuses → Available, Occupied, Reserved, Dirty.
                - Assign waiter to table.
                - Display tables in grid view (frontend).

            - Reservation system (customer name, phone, time).
        ✅ Deliverable: Admin can create tables, assign waiters, and see reservation dashboard.


###📍 Phase 3: Menu & Product Management
        🔹 Goal: Manage restaurant menu items.

       __Tasks:__
            - Categories (Starters, Drinks, Main Course, etc.).
            - Products CRUD (name, description, price, availability).
            - Add-ons & Modifiers (extra cheese, toppings).
            - Combo Meals / Packages / Set Menus.
            - Menu display in frontend with category filtering.
        ✅ Deliverable: Admin can manage menu; POS can display all menu items.

###📍 Phase 4: Order Management
        🔹 Goal: Enable waiters to take orders.

       __Tasks:__
            - Create Order → select table, assign waiter, add items.
            - Update Order → add/remove items, change qty.
            - Transfer order → move to another table.
            - Split orders (per person or per item).
            - Kitchen Order Ticket (KOT) auto-generated on order confirm.
        ✅ Deliverable: Waiter can take table orders, and kitchen staff sees them.

###📍 Phase 5: Kitchen Management (KDS)
        🔹 Goal: Kitchen staff can manage cooking flow.

       __Tasks:__
            - Kitchen Display Screen (KDS) → show pending orders.
            - Order Status flow → Pending → Cooking → Ready → Served.
            - Auto notifications when order ready.
        ✅ Deliverable: Kitchen team manages orders digitally.

###📍 Phase 6: Billing & Payments
        🔹 Goal: Complete the order lifecycle with billing.

       __Tasks:__
            - Apply tax, service charge, discounts.
            - Multiple payment methods (cash, card, mobile wallet).
            - Split bills (by seat or by item).
            - Generate digital receipt (print/PDF/email).
            - Refund/cancel order process.
        ✅ Deliverable: POS can generate bills and record payments.


###📍 Phase 6: Billing & Payments
        🔹 Goal: Complete the order lifecycle with billing.

       __Tasks:__
            - Apply tax, service charge, discounts.
            - Multiple payment methods (cash, card, mobile wallet).
            - Split bills (by seat or by item).
            - Generate digital receipt (print/PDF/email).
            - Refund/cancel order process.
        ✅ Deliverable: POS can generate bills and record payments.


###📍 Phase 7: Inventory & Stock
        🔹 Goal: Track stock usage and manage purchases.

       __Tasks:__
            - Manage ingredients/stock items.
            - Recipe-based stock deduction when items ordered.
            - Low stock alerts.
            - Supplier & purchase order management.
            - Wastage tracking.
        ✅ Deliverable: Inventory auto-reduces when food is sold.


###📍 Phase 8: Reports & Analytics
        🔹 Goal: Business insights.

       __Tasks:__
            - Sales reports (daily, weekly, monthly).
            - Waiter performance (orders served, tips collected).
            - Kitchen performance (prep time).
            - Inventory usage/wastage.
            - Profit/loss & most selling items.
        ✅ Deliverable: Admin dashboard with full analytics.


###📍 Phase 9: Advanced Features
        🔹 Optional but powerful add-ons.

       __Tasks:__
            - Customer QR code ordering (scan QR → view menu → place order).
            - Loyalty program (points, coupons).
            - Multi-branch management (franchise setup).
            - Offline mode (cache orders, sync when online).
            - Mobile app for waiters (tablet/phone ordering).
            - Hotel integration (if POS + Hotel management combined).
        ✅ Deliverable: Smart modern POS with extra business features.



###📐 Suggested Build Order (Milestones)
        - Core Auth & RBAC → Phase 1
        - Tables + Waiters → Phase 2
        - Menu + Products → Phase 3
        - Orders + Kitchen → Phase 4 & 5
        - Payments → Phase 6
        - Inventory → Phase 7
        - Reports → Phase 8
        - Advanced Features → Phase 9

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

###1. Database & Entity Setup

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