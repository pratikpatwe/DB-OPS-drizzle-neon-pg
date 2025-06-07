# 📝 Todo App - Next.js 15 + Neon DB + Drizzle ORM

A modern, full-stack todo application built with **Next.js 15**, **Neon DB (PostgreSQL)**, and **Drizzle ORM**. This project demonstrates best practices for building type-safe, production-ready web applications.


## ✨ Features

- ✅ **Create, Read, Update, Delete** todos
- ✅ **Mark todos as complete/incomplete**
- ✅ **Real-time UI updates**
- ✅ **Responsive design** with Tailwind CSS
- ✅ **Type-safe** with TypeScript
- ✅ **Database migrations** with Drizzle Kit
- ✅ **Error handling** and loading states
- ✅ **Modern React patterns** (hooks, functional components)

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| **Next.js 15** | React framework with App Router |
| **TypeScript** | Type safety and better DX |
| **Neon DB** | Serverless PostgreSQL database |
| **Drizzle ORM** | Type-safe database queries |
| **Tailwind CSS** | Utility-first CSS framework |
| **React Hooks** | State management |

## 🚀 Quick Start

### Prerequisites

- Node.js 18+ installed
- A [Neon](https://neon.tech) account (free tier available)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/pratikpatwe/DB-OPS-drizzle-neon-pg.git
   cd todo-app
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   ```bash
   cp .env.example .env.local
   ```
   Add your Neon database URL to `.env.local`:
   ```env
   DATABASE_URL=postgresql://username:password@host/database?sslmode=require
   ```

4. **Run database migrations**
   ```bash
   npm run db:generate
   npm run db:migrate
   ```

5. **Start the development server**
   ```bash
   npm run dev
   ```

6. **Open your browser**
   Navigate to [http://localhost:3000](http://localhost:3000)

## 📁 Project Structure

```
todo-app/
├── app/
│   ├── api/
│   │   └── todos/
│   │       ├── route.ts           # GET, POST /api/todos
│   │       └── [id]/
│   │           └── route.ts       # PATCH, DELETE /api/todos/[id]
│   ├── globals.css                # Global styles
│   ├── layout.tsx                 # Root layout
│   └── page.tsx                   # Home page component
├── lib/
│   └── db/
│       ├── index.ts               # Database connection
│       └── schema.ts              # Database schema
├── drizzle/                       # Migration files
├── .env.local                     # Environment variables
├── drizzle.config.ts              # Drizzle configuration
└── package.json
```

## 🗄️ Database Schema

```sql
CREATE TABLE todos (
  id SERIAL PRIMARY KEY,
  title TEXT NOT NULL,
  completed BOOLEAN DEFAULT FALSE NOT NULL,
  created_at TIMESTAMP DEFAULT NOW() NOT NULL,
  updated_at TIMESTAMP DEFAULT NOW() NOT NULL
);
```

## 🔧 Available Scripts

| Script | Description |
|--------|-------------|
| `npm run dev` | Start development server |
| `npm run build` | Build for production |
| `npm run start` | Start production server |
| `npm run lint` | Run ESLint |
| `npm run db:generate` | Generate database migrations |
| `npm run db:migrate` | Apply database migrations |

## 📡 API Endpoints

### Todos

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/todos` | Get all todos |
| `POST` | `/api/todos` | Create new todo |
| `PATCH` | `/api/todos/[id]` | Update todo |
| `DELETE` | `/api/todos/[id]` | Delete todo |

### Example Requests

**Create a todo:**
```bash
curl -X POST http://localhost:3000/api/todos \
  -H "Content-Type: application/json" \
  -d '{"title": "Learn Next.js"}'
```

**Update a todo:**
```bash
curl -X PATCH http://localhost:3000/api/todos/1 \
  -H "Content-Type: application/json" \
  -d '{"completed": true}'
```

## 🎨 UI Components

- **TodoForm**: Add new todos
- **TodoList**: Display all todos
- **TodoItem**: Individual todo with actions
- **Stats**: Show completion progress

## 🏆 Best Practices Implemented

### 🔒 Type Safety
- Full TypeScript integration
- Drizzle ORM type inference
- Proper API response types

### 🚨 Error Handling
- Try-catch blocks in API routes
- User-friendly error messages
- Proper HTTP status codes

### 🗃️ Database
- Proper schema design
- Efficient queries with ordering
- Database constraints and defaults

### 🎯 Performance
- Optimistic UI updates
- Minimal re-renders
- Efficient state management

### 🔐 Security
- Environment variable protection
- Input validation and sanitization
- SQL injection prevention

## 🚀 Deployment

### Vercel (Recommended)

1. **Push to GitHub**
   ```bash
   git add .
   git commit -m "Initial commit"
   git push origin main
   ```

2. **Deploy to Vercel**
   - Connect your GitHub repository
   - Add your `DATABASE_URL` environment variable
   - Deploy automatically

### Other Platforms
- **Railway**: Great for full-stack apps
- **Netlify**: For static deployment
- **DigitalOcean App Platform**: Container-based deployment

## 🔮 Future Enhancements

### Features
- [ ] User authentication (NextAuth.js)
- [ ] Todo categories and tags
- [ ] Due dates and reminders
- [ ] Search and filtering
- [ ] Drag & drop reordering
- [ ] Dark/light mode toggle
- [ ] Data export/import

### Technical
- [ ] Server Actions (Next.js 15)
- [ ] Real-time updates (WebSockets)
- [ ] Caching (React Query/SWR)
- [ ] Unit and integration tests
- [ ] Docker containerization
- [ ] CI/CD pipeline

## 🐛 Troubleshooting

### Common Issues

**Database connection errors:**
- Verify your `DATABASE_URL` is correct
- Ensure your Neon database is active
- Check if environment variables are loaded

**Migration issues:**
- Install `dotenv`: `npm install dotenv`
- Verify `drizzle.config.ts` loads environment variables

**TypeScript errors:**
- Run `npm run build` to check for type errors
- Ensure all imports use correct paths

**API routes not working:**
- Check file naming conventions
- Verify route structure matches URLs
- Check for typos in file paths

## 📚 Learning Resources

- [Next.js Documentation](https://nextjs.org/docs)
- [Drizzle ORM Guide](https://orm.drizzle.team/)
- [Neon Database Docs](https://neon.tech/docs)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/)
- [Tailwind CSS Docs](https://tailwindcss.com/docs)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Next.js Team](https://nextjs.org/) for the amazing framework
- [Neon](https://neon.tech/) for serverless PostgreSQL
- [Drizzle Team](https://orm.drizzle.team/) for the excellent ORM
- [Tailwind CSS](https://tailwindcss.com/) for the utility-first CSS

## 📞 Connect with Me

Built by **Pratik Patwe**

🐦 **Follow me on X (Twitter):** [@pratik_patwe](https://x.com/pratik_patwe)

---

⭐ **If this project helped you, please consider giving it a star!** ⭐