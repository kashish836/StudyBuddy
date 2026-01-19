# 📚 StudyBuddy

> **A Modern Platform for Finding Study Partners and Collaborating on Learning Goals**

![Django](https://img.shields.io/badge/django-%23092E20.svg?style=for-the-badge&logo=django&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Azure](https://img.shields.io/badge/azure-%230072C6.svg?style=for-the-badge&logo=microsoftazure&logoColor=white)
![SQLite](https://img.shields.io/badge/sqlite-%2307405e.svg?style=for-the-badge&logo=sqlite&logoColor=white)
![Github Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![DjangoREST](https://img.shields.io/badge/DJANGO-REST-ff1709?style=for-the-badge&logo=django&logoColor=white&color=ff1709&labelColor=gray)

---

## 📖 Table of Contents

- [About the Project](#-about-the-project)
- [Features](#-features)
- [Prerequisites](#-prerequisites)
- [Installation](#-installation)
- [Project Structure](#-project-structure)
- [API Documentation](#-api-documentation)
- [Screenshots](#-screenshots)
- [Demo](#-demo)
- [Bug Reports](#-bug-reports)
- [Contributing](#-contributing)
- [Acknowledgments](#-acknowledgments)
- [Author](#-author)
- [Support](#-support)

---


## 🎯 About the Project

### Problem Statement
Students often struggle to find motivated study partners for specific topics. Traditional methods like asking classmates are inefficient and limit opportunities for collaboration. Many students feel isolated in their learning journey and lack structured spaces to connect with peers who share similar academic goals.

### Our Solution
**StudyBuddy** is a comprehensive web application that bridges this gap by creating a dynamic community where students can:
- 🔍 Discover study partners across various academic subjects
- 👥 Create and join study groups focused on specific topics
- 🤝 Connect with like-minded learners in a structured environment
- 💡 Share knowledge and collaborate effectively

Built with modern technologies and deployed on cloud infrastructure, StudyBuddy provides a seamless, responsive experience accessible from any device. The platform emphasizes ease of use while maintaining robust functionality for serious academic collaboration.

### Tech Stack
- **Backend:** Django, Django REST Framework
- **Frontend:** HTML5, CSS3, JavaScript
- **Database:** SQLite (Development), PostgreSQL (Production-ready)
- **Containerization:** Docker
- **CI/CD:** GitHub Actions
- **Cloud Deployment:** Microsoft Azure

---

## ✨ Features

- **🎯 Intuitive User Interface** - Simple, clean design that requires minimal learning curve for students of all technical backgrounds
- **🐳 Docker Containerization** - Fully containerized application ensuring consistency across different environments
- **🔄 CI/CD Pipeline** - Automated testing and deployment using GitHub Actions for rapid development cycles
- **☁️ Cloud Deployment** - Production-ready deployment on Microsoft Azure for scalability and reliability
- **📱 Fully Responsive** - Seamless experience across desktop, tablet, and mobile devices
- **🔐 User Authentication** - Secure login and signup system with personalized user profiles
- **🏫 Study Room Management** - Create or join study rooms for specific topics and collaborate in real-time
- **👤 User Profiles** - Customize your profile with bio, avatar, and academic interests
- **🔎 Advanced Search** - Find study topics and partners with powerful search and filtering capabilities
- **📊 Activity Feed** - Stay updated with recent activities and discussions in the community
- **📝 Real-time Messaging** - Communicate with study partners and group members instantly

---

## � Prerequisites

Before you begin, ensure you have the following installed on your machine:

| Software | Version | Download |
|----------|---------|----------|
| Python | 3.8+ | [python.org](https://www.python.org/downloads/) |
| Git | Latest | [git-scm.com](https://git-scm.com/downloads) |
| pip | Latest | Included with Python |
| Docker *(Optional)* | Latest | [docker.com](https://www.docker.com/products/docker-desktop) |
| Virtual Environment | - | Built-in with Python 3.3+ |

### System Requirements
- **OS:** Windows, macOS, or Linux
- **RAM:** Minimum 2GB (4GB recommended)
- **Disk Space:** At least 500MB for dependencies and database

---

## 📦 Installation

Choose one of the following installation methods:

### Option 1: Local Development Setup (Recommended for Development)

#### Step 1: Clone the Repository
```bash
git clone https://github.com/abhikalparya/StudyBuddy.git
cd StudyBuddy
```

#### Step 2: Create Virtual Environment
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

#### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

#### Step 4: Apply Database Migrations
```bash
python manage.py migrate
```

#### Step 5: Create Superuser (Admin Account)
```bash
python manage.py createsuperuser
```
Follow the prompts to create your admin account.

#### Step 6: Run Development Server
```bash
python manage.py runserver
```

The application will be available at `http://localhost:8000`

#### Step 7: Access Admin Panel
Navigate to `http://localhost:8000/admin` and log in with your superuser credentials.

---

### Option 2: Docker Installation (Recommended for Deployment)

#### Prerequisites for Docker
- Docker Desktop installed and running on your machine

#### Step 1: Clone the Repository
```bash
git clone https://github.com/abhikalparya/StudyBuddy.git
cd StudyBuddy
```

#### Step 2: Build Docker Image
```bash
docker build -t studybuddy:latest .
```

#### Step 3: Run Docker Container
```bash
docker run -p 8000:8000 -e DEBUG=False studybuddy:latest
```

#### Step 4: Access the Application
Open your browser and navigate to `http://localhost:8000`

#### Optional: Using Docker Compose
Create a `docker-compose.yml` file for production deployment:
```yaml
version: '3.8'
services:
  web:
    build: .
    ports:
      - "8000:8000"
    environment:
      - DEBUG=False
      - SECRET_KEY=your_secret_key_here
    volumes:
      - ./:/app
```

Then run:
```bash
docker-compose up --build
```

---

## 📁 Project Structure

```
StudyBuddy/
├── manage.py                      # Django project management script
├── requirements.txt               # Python dependencies
├── Dockerfile                     # Docker configuration
├── README.md                      # Project documentation
├── LICENSE                        # Project license
│
├── StudyBuddy/                    # Main Django project settings
│   ├── settings.py               # Django settings & configurations
│   ├── urls.py                   # Main URL routing
│   ├── wsgi.py                   # WSGI configuration for deployment
│   └── asgi.py                   # ASGI configuration
│
├── base/                          # Main Django application
│   ├── models.py                 # Database models (User, Room, Message)
│   ├── views.py                  # View logic and request handlers
│   ├── urls.py                   # App URL routing
│   ├── forms.py                  # Django forms for user input
│   ├── admin.py                  # Django admin configuration
│   ├── apps.py                   # App configuration
│   │
│   ├── api/                      # REST API endpoints
│   │   ├── views.py             # API view logic
│   │   ├── serializers.py       # DRF serializers
│   │   └── urls.py              # API routing
│   │
│   ├── migrations/              # Database migrations
│   │   ├── 0001_initial.py
│   │   ├── 0002_user_bio_user_name_alter_user_email.py
│   │   └── 0003_user_avatar.py
│   │
│   └── templates/               # HTML templates
│       └── base/
│           ├── home.html        # Homepage
│           ├── room.html        # Study room details
│           ├── profile.html     # User profile page
│           ├── login_register.html  # Authentication pages
│           ├── room_form.html   # Room creation/editing
│           └── ...              # Other templates
│
├── templates/                     # Base templates
│   ├── main.html                # Main base template
│   └── navbar.html              # Navigation component
│
└── static/                        # Static files
    ├── css/
    │   ├── style.css
    │   └── main.css
    ├── js/
    │   └── script.js
    └── images/
        └── icons/
```

### Model Overview

**User Model**
- Extended Django User model with bio, name, and avatar
- Tracks user activity and study preferences

**Room Model**
- Study room entity with topic, description, and participants
- Supports many-to-many relationships for users

**Message Model**
- Stores messages between study group members
- Includes timestamps and author information

---

## 🔌 API Documentation

### Base URL
```
http://localhost:8000/api/
```

### Authentication
All API endpoints support both session and token-based authentication.

### Available Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|----------------|
| GET | `/users/` | List all users | Yes |
| GET | `/users/<id>/` | Get user details | Yes |
| GET | `/rooms/` | List all study rooms | No |
| GET | `/rooms/<id>/` | Get room details | No |
| POST | `/rooms/` | Create a new room | Yes |
| PUT | `/rooms/<id>/` | Update room | Yes |
| DELETE | `/rooms/<id>/` | Delete room | Yes |
| GET | `/messages/` | List messages | Yes |
| POST | `/messages/` | Create message | Yes |

### Example API Requests

#### Get All Rooms
```bash
curl -X GET http://localhost:8000/api/rooms/
```

**Response:**
```json
{
  "count": 2,
  "next": null,
  "previous": null,
  "results": [
    {
      "id": 1,
      "name": "Python Learning",
      "description": "Learn Python programming",
      "topic": "Programming",
      "participants_count": 5,
      "created_at": "2024-01-15T10:30:00Z"
    }
  ]
}
```

#### Create a Room
```bash
curl -X POST http://localhost:8000/api/rooms/ \
  -H "Content-Type: application/json" \
  -H "Authorization: Token YOUR_TOKEN_HERE" \
  -d '{
    "name": "Advanced Django",
    "description": "Deep dive into Django ORM",
    "topic": "Web Development"
  }'
```

**Response:**
```json
{
  "id": 3,
  "name": "Advanced Django",
  "description": "Deep dive into Django ORM",
  "topic": "Web Development",
  "created_at": "2024-01-20T14:22:00Z",
  "created_by": "john_doe"
}
```

#### Get User Profile
```bash
curl -X GET http://localhost:8000/api/users/1/ \
  -H "Authorization: Token YOUR_TOKEN_HERE"
```

**Response:**
```json
{
  "id": 1,
  "username": "john_doe",
  "email": "john@example.com",
  "bio": "Computer Science student",
  "avatar": "https://example.com/avatar.jpg",
  "rooms_created": 3,
  "rooms_joined": 8,
  "joined_date": "2024-01-01T00:00:00Z"
}
```

---

## 📸 Screenshots

<details>
<summary><b>🖼️ Click to view screenshots</b></summary>

#### Login Page
![login-page](https://user-images.githubusercontent.com/81465377/216761524-6e08761a-7d7d-40b6-9949-ba2bdc0a5a2a.jpg)

#### Signup Page
![signup-page](https://user-images.githubusercontent.com/81465377/216761550-02830aa7-c529-413c-b8e1-4436a02fe910.jpg)

#### Home Page
![home](https://user-images.githubusercontent.com/81465377/216761576-5e4621d2-953d-41ad-b8dd-6f5ff65993ef.jpg)

#### Profile Page
![profile](https://user-images.githubusercontent.com/81465377/216761593-c2085db8-b5a1-4a5b-80df-759d2224ac14.jpg)

#### Create Study Room
![create-room](https://user-images.githubusercontent.com/81465377/216761626-c729058a-5609-4478-845c-418fb95c4085.jpg)

#### Study Room
![room](https://user-images.githubusercontent.com/81465377/216761652-35407aa9-1dff-406b-86fc-df1659b6f4d8.jpg)

#### Edit Profile
![edit-profile](https://user-images.githubusercontent.com/81465377/216761663-86396871-c40c-41e2-a9b9-3f5a8b0dcee7.jpg)

</details>

---

## 🎥 Demo

Check out our project in action! Watch the video demonstration below:

![Youtube](https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white)

[![StudyBuddy Demo Video](https://img.youtube.com/vi/GReHXtIDayg/0.jpg)](https://www.youtube.com/watch?v=GReHXtIDayg)

---

## 🐛 Bug Reports

If you encounter any issues or bugs, please help us improve by reporting them:

### How to Report a Bug

1. **Check Existing Issues** - Search [GitHub Issues](https://github.com/abhikalparya/StudyBuddy/issues) to see if your bug has been reported
2. **Provide Clear Description** - Explain what you were trying to do and what happened
3. **Include Environment Info** - Mention your OS, Python version, and browser (if applicable)
4. **Add Steps to Reproduce** - Provide step-by-step instructions to reproduce the issue
5. **Include Screenshots/Logs** - Attach relevant screenshots or error logs
6. **Submit Issue** - Open a new issue with the title format: `[BUG] Brief description`

### Report Format
```markdown
**Description:** What went wrong?
**Environment:** OS, Python version, Browser
**Steps to Reproduce:**
1. Step 1
2. Step 2
**Expected Behavior:** What should happen?
**Actual Behavior:** What actually happened?
**Screenshots:** [If applicable]
```

---

## 🤝 Contributing

We welcome contributions! To contribute to StudyBuddy:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Commit your changes (`git commit -m 'Add amazing feature'`)
5. Push to the branch (`git push origin feature/amazing-feature`)
6. Open a Pull Request

Please ensure your code follows PEP 8 standards and includes appropriate tests.

---

## 🙏 Acknowledgments

We'd like to thank:

- **Django Community** - For the robust web framework
- **All Contributors** - Who have helped improve this project
- **Open Source Community** - For the amazing tools and libraries used
- **Our Users** - For using and providing feedback on StudyBuddy

### Built With

- [Django](https://www.djangoproject.com/) - Web framework
- [Django REST Framework](https://www.django-rest-framework.org/) - REST API
- [Docker](https://www.docker.com/) - Containerization
- [GitHub Actions](https://github.com/features/actions) - CI/CD
- [Microsoft Azure](https://azure.microsoft.com/) - Cloud hosting

---

## ✍️ Author

**Abhi Kalparya**

- GitHub: [@abhikalparya](https://github.com/abhikalparya)
- Email: Contact for inquiries
- LinkedIn: Your LinkedIn profile

---

## 💬 Support

### Getting Help

- 📖 **Documentation** - Check the [Wiki](https://github.com/abhikalparya/StudyBuddy/wiki) for detailed guides
- 🐛 **Issues** - Search [GitHub Issues](https://github.com/abhikalparya/StudyBuddy/issues) for solutions
- 💬 **Discussions** - Join [GitHub Discussions](https://github.com/abhikalparya/StudyBuddy/discussions) for questions
- 📧 **Email** - Reach out directly with specific questions

### Support the Project

If you find StudyBuddy helpful, please consider:
- ⭐ Starring the repository
- 🍴 Forking and contributing
- 📣 Sharing with your network
- 💰 Sponsoring development (if applicable)

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

### Permissions
- ✅ Commercial use
- ✅ Modification
- ✅ Distribution
- ✅ Private use
- ❌ Liability
- ❌ Warranty

---

## 🚀 Roadmap

### Future Features
- [ ] Advanced notification system
- [ ] Video conferencing integration
- [ ] Study progress tracking
- [ ] AI-powered study partner recommendations
- [ ] Mobile app (iOS/Android)
- [ ] Gamification features (badges, achievements)
- [ ] Group calendar and scheduling
- [ ] File sharing and collaborative documents
- [ ] Study material library
- [ ] Performance analytics dashboard

---

## 📞 Quick Links

- [Home Page](http://localhost:8000)
- [Admin Panel](http://localhost:8000/admin)
- [GitHub Repository](https://github.com/abhikalparya/StudyBuddy)
- [Report a Bug](https://github.com/abhikalparya/StudyBuddy/issues/new)
- [Request a Feature](https://github.com/abhikalparya/StudyBuddy/discussions)

---

<div align="center">

**Made with ❤️ by Abhi Kalparya**

⭐ Don't forget to star the repository if you found it helpful!

</div>
