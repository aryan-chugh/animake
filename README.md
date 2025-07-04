# 🎬 Animake - Online Video Editor

A comprehensive web-based video editing platform built with Flask that allows users to create, edit, and manage videos through an intuitive web interface.

## 🚀 Features

### 🎥 Video Creation & Editing
- **Timeline-based Video Editor**: Drag-and-drop interface for creating videos from images
- **Image-to-Video Conversion**: Transform static images into dynamic video content
- **Custom Transitions**: Multiple transition effects (fade, slide, zoom, crop)
- **Audio Integration**: Add background music and audio tracks to videos
- **Video Quality Control**: Adjust resolution, FPS, and bitrate
- **Real-time Preview**: Preview videos before final rendering

### 👤 User Management
- **User Authentication**: Secure login/signup with JWT tokens
- **Profile Management**: User profiles with image upload capability
- **Password Recovery**: Email-based password reset with OTP verification
- **Session Management**: Persistent user sessions with security

### 📊 Dashboard & Admin
- **User Dashboard**: View and manage past projects
- **Project History**: Timeline view of created videos with thumbnails
- **Admin Panel**: User management and system administration
- **Analytics**: Track user activity and project statistics

### 🛠️ Technical Features
- **Multi-format Support**: JPEG, PNG image uploads
- **Cloud Storage**: PostgreSQL database with blob storage
- **Email Integration**: SendGrid for password reset emails
- **Responsive Design**: Works on desktop and mobile devices
- **Background Processing**: Asynchronous video rendering

## 🏗️ Architecture

### Backend (Flask)
```
animake/
├── app.py                 # Main Flask application
├── requirements.txt       # Python dependencies
├── root.crt              # SSL certificate
└── myenv/                # Python virtual environment
```

### Frontend Structure
```
static/
├── admin/                # Admin panel assets
├── dashboard/            # Dashboard UI components
├── homepage/             # Landing page assets
├── login/               # Authentication pages
├── upload_page/         # File upload interface
├── videopage/           # Video editor interface
├── loader/              # Loading animations
└── user_videos/         # Generated video storage
```

### Templates
```
templates/
├── admin/               # Admin panel templates
├── dashboard/           # Dashboard HTML templates
├── homepage/            # Landing page template
├── login/              # Authentication forms
├── upload_page/        # Upload interface
└── videopage/          # Video editor interface
```

## 🔧 Installation & Setup

### Prerequisites
- Python 3.8+
- PostgreSQL (CockroachDB)
- Virtual environment support

### Installation Steps

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd animake
   ```

2. **Create and activate virtual environment**
   ```bash
   python -m venv myenv
   
   # Windows
   myenv\Scripts\activate
   
   # macOS/Linux
   source myenv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Database Setup**
   - Configure PostgreSQL connection in `app.py`
   - Update connection string with your database credentials
   - Run the application to create necessary tables

5. **Environment Configuration**
   ```bash
   # Set environment variables
   export SECRET_KEY="your-secret-key"
   export SENDGRID_API_KEY="your-sendgrid-api-key"
   ```

6. **Run the application**
   ```bash
   python app.py
   ```

## 📦 Dependencies

### Core Framework
- **Flask**: Web framework
- **Flask-Bcrypt**: Password hashing
- **Flask-JWT-Extended**: JWT authentication
- **psycopg2**: PostgreSQL adapter

### Video Processing
- **MoviePy**: Video editing and processing
- **OpenCV**: Computer vision operations
- **imageio**: Image I/O operations
- **numpy**: Numerical computing

### Additional Libraries
- **SendGrid**: Email service
- **itsdangerous**: Secure token generation
- **Gunicorn**: WSGI server for production

## 🗄️ Database Schema

### Users Table
- `id`: Primary key
- `name`: Username
- `email`: Email address
- `password`: Hashed password
- `role`: User role (user/admin)
- `profile_image`: Profile picture blob
- `last_login`: Last login timestamp

### Projects Table
- `username`: Project owner
- `project_name`: Project identifier
- `img_frame`: Video thumbnail
- `created`: Creation timestamp
- `duration`: Video duration

### Media Tables
- `proj_imgs`: User uploaded images
- `audio_files`: Audio tracks and background music

## 🎨 User Interface

### Landing Page
- Modern, responsive design
- Clear call-to-action buttons
- Video editing preview

### Video Editor
- Timeline-based editing interface
- Drag-and-drop functionality
- Real-time preview
- Multiple transition options
- Audio track management

### Dashboard
- Project gallery view
- Video thumbnails with metadata
- Quick access to edit/delete projects
- User profile management

## 🔐 Security Features

- **JWT Authentication**: Secure token-based authentication
- **Password Hashing**: Bcrypt password encryption
- **SQL Injection Protection**: Parameterized queries
- **File Upload Validation**: Type and size restrictions
- **Session Management**: Secure session handling

## 🚀 API Endpoints

### Authentication
- `POST /login` - User login
- `POST /signup` - User registration
- `GET /logout` - User logout
- `POST /forgot_password` - Password reset

### Video Management
- `POST /create_movie/<username>` - Create video from images
- `POST /upload` - Upload images
- `GET /retrieve_images/<user>` - Get user images
- `POST /save_frame` - Save video thumbnail

### User Management
- `GET /dashboard` - User dashboard
- `GET /admin` - Admin panel
- `DELETE /delete_user/<username>` - Delete user
- `PUT /update_user_name/<username>` - Update username

## 🔮 Future Enhancements

- **Advanced Effects**: More transition and filter options
- **Collaboration**: Multi-user project editing
- **Templates**: Pre-built video templates
- **Export Options**: Multiple output formats
- **Mobile App**: Native mobile application
- **AI Integration**: Automated video generation

## 📝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 🔧 Development Setup

### Local Development
```bash
# Start development server
python app.py

# Access application
http://localhost:5000
```
