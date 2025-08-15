# Online Quiz System

A comprehensive web-based quiz management system built with Django that allows administrators, teachers, and students to manage and participate in online quizzes.

## Features

### 🎯 Multi-Role System
- **Admin**: Complete system management
- **Teacher**: Create and manage quizzes
- **Student**: Take quizzes and view results

### 📚 Core Functionality
- **Course Management**: Create and organize quiz courses
- **Question Bank**: Add multiple-choice questions with 4 options
- **Quiz Taking**: Timed quiz sessions for students
- **Result Tracking**: Automatic scoring and result management
- **User Management**: Registration, authentication, and profile management

### 🔐 Admin Features
- Dashboard with system statistics
- Teacher approval system with salary management
- Student management and monitoring
- Course and question management
- View and analyze student performance
- Email notifications for contact form submissions

### 👨‍🏫 Teacher Features
- Create and manage courses
- Add questions to courses
- View student results
- Profile management with image upload
- Approval-based registration system

### 👨‍🎓 Student Features
- Browse available courses
- Take timed quizzes
- View quiz results and performance history
- Profile management with image upload
- Responsive quiz interface

## Technology Stack

- **Backend**: Django 3.x
- **Database**: SQLite (development)
- **Frontend**: HTML5, CSS3, Bootstrap 5, JavaScript
- **Authentication**: Django's built-in authentication system
- **File Handling**: Django's file upload system
- **Email**: SMTP integration for contact form

## Installation

### Prerequisites
- Python 3.7+
- pip (Python package manager)

### Setup Instructions

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd "Online Quiz System"
   ```

2. **Create and activate virtual environment**
   ```bash
   python -m venv .venv
   
   # On Windows
   .venv\Scripts\activate
   
   # On macOS/Linux
   source .venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install django
   pip install django-widget-tweaks
   pip install django-bootstrap5
   pip install Pillow  # For image handling
   ```

4. **Configure email settings (optional)**
   
   Edit [`onlinequiz/settings.py`](onlinequiz/settings.py:134) and update email configuration:
   ```python
   EMAIL_HOST_USER = 'your-email@gmail.com'
   EMAIL_HOST_PASSWORD = 'your-app-password'
   EMAIL_RECEIVING_USER = ['admin@example.com']
   ```

5. **Run database migrations**
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

6. **Create superuser (admin)**
   ```bash
   python manage.py createsuperuser
   ```

7. **Run the development server**
   ```bash
   python manage.py runserver
   ```

8. **Access the application**
   - Open your browser and go to `http://127.0.0.1:8000/`
   - Admin panel: `http://127.0.0.1:8000/admin/`

## Project Structure

```
Online Quiz System/
├── manage.py                 # Django management script
├── db.sqlite3               # SQLite database (auto-generated)
├── .venv/                   # Virtual environment
├── onlinequiz/              # Main project directory
│   ├── settings.py          # Django settings
│   ├── urls.py              # Main URL configuration
│   ├── wsgi.py              # WSGI configuration
│   └── asgi.py              # ASGI configuration
├── quiz/                    # Core quiz app
│   ├── models.py            # Course, Question, Result models
│   ├── views.py             # Main application views
│   ├── forms.py             # Django forms
│   └── admin.py             # Admin interface configuration
├── student/                 # Student management app
│   ├── models.py            # Student model
│   ├── views.py             # Student-specific views
│   ├── forms.py             # Student forms
│   └── urls.py              # Student URL patterns
├── teacher/                 # Teacher management app
│   ├── models.py            # Teacher model
│   ├── views.py             # Teacher-specific views
│   ├── forms.py             # Teacher forms
│   └── urls.py              # Teacher URL patterns
├── templates/               # HTML templates
│   ├── quiz/                # Quiz-related templates
│   ├── student/             # Student templates
│   └── teacher/             # Teacher templates
└── static/                  # Static files
    ├── image/               # UI images
    ├── profile_pic/         # User profile pictures
    └── screenshots/         # Application screenshots
```

## Usage Guide

### For Administrators
1. Login at `/adminlogin` or use Django admin panel
2. Manage teachers (approve/reject registrations, set salaries)
3. Monitor students and their performance
4. Create and manage courses
5. Add questions to courses
6. View system statistics on the dashboard

### For Teachers
1. Register at `/teacher/teachersignup`
2. Wait for admin approval
3. Login at `/teacher/teacherlogin`
4. Create courses and add questions
5. Monitor student performance

### For Students
1. Register at `/student/studentsignup`
2. Login at `/student/studentlogin`
3. Browse available courses
4. Take quizzes and view results
5. Track your performance over time

## Key Models

### Course Model
- Course name and description
- Number of questions and total marks
- Used to organize quiz content

### Question Model
- Multiple-choice questions with 4 options
- Associated with specific courses
- Configurable marks per question

### Student/Teacher Models
- Extended user profiles with additional fields
- Profile picture upload functionality
- Role-based access control

### Result Model
- Tracks quiz attempts and scores
- Links students to their course results
- Timestamp tracking for attempts

## Configuration

### Email Setup
To enable contact form functionality, configure SMTP settings in [`settings.py`](onlinequiz/settings.py:130):

1. Use Gmail SMTP or your preferred email service
2. Enable "Less secure app access" for Gmail (or use App Passwords)
3. Update the email configuration variables

### Security Notes
- Change the [`SECRET_KEY`](onlinequiz/settings.py:18) in production
- Set [`DEBUG = False`](onlinequiz/settings.py:21) in production
- Configure proper [`ALLOWED_HOSTS`](onlinequiz/settings.py:23) for production
- Use environment variables for sensitive information

## Screenshots

The application includes several interface screenshots in [`static/screenshots/`](static/screenshots/):
- Homepage interface
- Admin dashboard
- Teacher interface
- Exam taking interface
- Rules and guidelines

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/new-feature`)
5. Create a Pull Request

## License

This project is open source and available under the [MIT License](LICENSE).

## Support

For support and questions:
- Create an issue in the repository
- Contact the development team
- Check the documentation and code comments

## Future Enhancements

- [ ] Add timer functionality for quizzes
- [ ] Implement question randomization
- [ ] Add support for different question types
- [ ] Include detailed analytics and reporting
- [ ] Add bulk question import functionality
- [ ] Implement quiz categories and difficulty levels
- [ ] Add mobile-responsive improvements
- [ ] Include real-time notifications