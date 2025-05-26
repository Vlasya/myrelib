# 📚 myReLib

A personal book library manager with cloud storage and EPUB/PDF reading support.

## 📌 Project Description
This is a full-stack application built with:
- **Frontend**: React + Chakra UI
- **Backend**: NestJS + Prisma
- **Database**: PostgreSQL
- **Containerization**: Docker + Docker Compose
- **ORM**: Prisma
- **Authentication**: JWT (registration, login)
- **Book formats**: EPUB, PDF

---

## 📂 Repository Structure
```
myrelib/
├── client/ # React frontend (Chakra UI)
├── server/ # NestJS backend with Prisma
├── docker-compose.yml # Global Compose file
│── .gitignore
│── README.md
│── docker-compose.yml
```

---

## 🚀 How to Run the Project

### **1. Clone the Repository**
```bash
git clone <repo-url>
cd <repo-folder>
```

### **2. Configure the Environment Variables**
Create a `.env` file inside the `server` folder and set up the database connection:
```ini
DATABASE_URL="postgresql://postgres:password@localhost:5432/ai-task-manager?schema=public"
```


### **3. Start the Project with Docker**
Ensure you have **Docker** installed and running. Then, execute:
```bash
docker-compose up -d --build
```
Alternatively, if you're using a newer Docker version with built-in Compose: (Slightly more formal)
```bash
docker compose up -d --build
```
Stop all:
```bash
docker-compose down
```
or
```bash
docker compose down
    ```

This will set up PostgreSQL, run migrations, and start both frontend and backend services.

---
## Database Migrations (Prisma)

After the database container (`myrelib-db`) and server container (`server`) are running, you may need to apply Prisma migrations to create tables in the database.

1.  **Apply Migrations:**
    Run the following command in your terminal (the `server` container must be running):

    ```bash
    docker-compose exec server npx prisma migrate dev
    ```

    Or, if you're using a newer Docker version with integrated Compose:

    ```bash
    docker compose exec server npx prisma migrate dev
    ```

    This command will execute all unapplied migrations and update your database schema. If no migrations exist yet, it will prompt you to create the first one based on your `prisma/schema.prisma`.

2.  **Generate Prisma Client:**
    The Prisma Client is automatically generated when you install dependencies or run migrations. If you need to generate it manually:

    ```bash
    docker-compose exec server npx prisma generate
    ```

    Or, if you're using a newer Docker version with integrated Compose:

    ```bash
    docker compose exec server npx prisma generate
    ```
3. **Open Prisma Studio :**
```bash
npx prisma studio
```


### **5. Access the Application**
- **Frontend** runs at `http://localhost:5173`
- **Backend** runs at `http://localhost:3000`
- **PostgreSQL** is available at `localhost:5432`

---


📜 License
MIT — made with ❤️ by Albina

