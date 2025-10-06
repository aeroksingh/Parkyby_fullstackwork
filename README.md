# Parkyby Full Stack Application

A complete parking management system built with Django REST Framework (backend) and React + TypeScript (frontend).

## 🚀 Project Structure

```
Parkyby_fullstackwork/
├── parkby_backend/backend/
│   ├── apps/
│   │   ├── users/          # User authentication & management
│   │   └── parking/        # Parking spaces, vehicles & bookings
│   ├── backend/
│   │   ├── settings.py     # ✅ Django settings with DRF, CORS, JWT
│   │   └── urls.py         # ✅ Main URL configuration
│   ├── requirements.txt    # ✅ Python dependencies
│   ├── .env.example        # ✅ Environment variables template
│   └── manage.py
└── parkby_frontend/        # React + TypeScript + Vite application
```

## 📋 Prerequisites

- Python 3.8+
- Node.js 16+
- SQLite (included with Python)

## 🔧 Backend Setup

### 1. Navigate to backend directory
```bash
cd parkby_backend/backend
```

### 2. Create virtual environment
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Configure environment
```bash
cp .env.example .env
# Edit .env with your settings
```

### 5. Create app directories (if not exist)
```bash
mkdir -p apps/users apps/parking
touch apps/__init__.py
touch apps/users/__init__.py apps/parking/__init__.py
```

### 6. Run migrations
```bash
python manage.py makemigrations
python manage.py migrate
```

### 7. Create superuser
```bash
python manage.py createsuperuser
```

### 8. Run development server
```bash
python manage.py runserver
```

Backend will be available at: `http://localhost:8000`

## 🎨 Frontend Setup

### 1. Navigate to frontend directory
```bash
cd parkby_frontend
```

### 2. Install dependencies
```bash
npm install
```

### 3. Configure environment
```bash
cp .env.local.example .env.local
# Ensure VITE_API_BASE_URL=http://localhost:8000
```

### 4. Run development server
```bash
npm run dev
```

Frontend will be available at: `http://localhost:5173`

## 📚 API Endpoints

### Authentication
- `POST /api/auth/register/` - User registration
- `POST /api/auth/login/` - User login (returns JWT tokens)
- `POST /api/auth/refresh/` - Refresh access token
- `GET /api/auth/profile/` - Get user profile

### Parking Spaces
- `GET /api/parking/spaces/` - List all parking spaces
- `POST /api/parking/spaces/` - Create parking space (owner only)
- `GET /api/parking/spaces/{id}/` - Get parking space details
- `GET /api/parking/spaces/{id}/available-slots/` - Check availability

### Vehicles
- `GET /api/parking/vehicles/` - List user's vehicles
- `POST /api/parking/vehicles/` - Add new vehicle

### Bookings
- `GET /api/parking/bookings/` - List user's bookings
- `POST /api/parking/bookings/` - Create new booking
- `POST /api/parking/bookings/{id}/check-in/` - Check in to parking
- `POST /api/parking/bookings/{id}/check-out/` - Check out from parking

## 🔐 Features

### Backend
- ✅ JWT Authentication
- ✅ Custom User model with roles (customer/owner)
- ✅ RESTful API with DRF
- ✅ CORS configured for frontend
- ✅ SQLite database
- ✅ Admin panel at `/admin/`

### Frontend
- 🎨 Modern React with TypeScript
- 🔒 Protected routes
- 📱 Responsive design
- 🎯 Real-time booking management
- 🚗 Vehicle management
- 📊 Dashboard views

## 🛠️ Technology Stack

### Backend
- Django 4.2.7
- Django REST Framework 3.14.0
- Simple JWT 5.3.0
- Django CORS Headers 4.3.0
- Python Decouple 3.8

### Frontend
- React 18
- TypeScript
- Vite
- React Router
- Axios
- Tailwind CSS

## 📝 Environment Variables

### Backend (.env)
```
SECRET_KEY=your-secret-key-here
DEBUG=True
ALLOWED_HOSTS=localhost,127.0.0.1
CORS_ALLOWED_ORIGINS=http://localhost:3000,http://localhost:5173
```

### Frontend (.env.local)
```
VITE_API_BASE_URL=http://localhost:8000
```

## 🚦 Development Workflow

1. Start backend server: `python manage.py runserver`
2. Start frontend server: `npm run dev`
3. Access frontend at `http://localhost:5173`
4. API available at `http://localhost:8000/api/`
5. Admin panel at `http://localhost:8000/admin/`

## 📖 Additional Setup Notes

### Creating App Files

The backend apps (users and parking) need their model, serializer, view, and URL files created. See the SETUP.md file for complete code for each file.

### Frontend API Integration

The frontend needs API client files in `src/api/` directory:
- `client.ts` - Axios instance with JWT interceptor
- `auth.ts` - Authentication endpoints
- `parking.ts` - Parking space endpoints
- `vehicles.ts` - Vehicle endpoints
- `bookings.ts` - Booking endpoints

See SETUP.md for complete implementation.

## 🤝 Contributing

This is a full-stack parking management project. Feel free to contribute!

## 📄 License

MIT License

## 👤 Author

aeroks ingh

## 🎯 Next Steps

1. Complete app file creation (see SETUP.md)
2. Run migrations
3. Create test data
4. Configure frontend API integration
5. Test all endpoints
6. Deploy to production

---

**Status**: Backend configuration complete ✅ | App files need creation 🚧 | Frontend integration needed 🚧
