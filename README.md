# hrms
🚀 Enterprise HR Management System A scalable Angular app for enterprise-grade Human Resource Management. Features include modern UI/UX, role-based access control, advanced analytics, recruitment tools, and high-performance architecture with responsive design and top-tier security.
# Enterprise HR Management System

A comprehensive, enterprise-grade Angular application for Human Resource Management with advanced features, role-based access control, and modern UI/UX design.

## 🚀 Quick Start

### Prerequisites

- **Node.js** (v18.0.0 or higher)
- **npm** (v9.0.0 or higher)
- **Angular CLI** (v17.0.0 or higher)
- **Git** for version control

### Installation

\`\`\`bash
# Clone the repository
git clone <repository-url>
cd enterprise-hr-system

# Install dependencies
npm install

# Install Angular CLI globally (if not already installed)
npm install -g @angular/cli

# Start development server
npm start
\`\`\`

The application will be available at `http://localhost:4200`



## 🎯 Features by Role

### 🔐 Super Admin
- **Complete System Control**
  - User management (create, edit, delete, activate/deactivate)
  - Role and permission management
  - System configuration and settings
  - Database backup and restore
  - Audit log monitoring
  - Performance analytics
  - Security settings management

### 👨‍💼 Admin
- **Administrative Functions**
  - User management (limited)
  - Department management
  - Job category management
  - System reports and analytics
  - Bulk operations
  - Data export/import

### 🏢 HR/Recruiter
- **Recruitment Management**
  - Job posting creation and management
  - Candidate profile management
  - Interview scheduling and coordination
  - Application tracking and status updates
  - Resume parsing and analysis
  - Communication with candidates
  - Recruitment analytics and reports

### 👔 HOD (Head of Department)
- **Department Operations**
  - View department-specific job postings
  - Interview participation and feedback
  - Team member application reviews
  - Department analytics
  - Approval workflows

### 👤 Applicant
- **Job Application Portal**
  - Job search with advanced filters
  - Application submission and tracking
  - Profile management
  - Interview scheduling
  - Document upload and management
  - Communication with recruiters



## 🏗️ Admin Dashboard Features

### Dashboard Overview
- **Real-time Statistics**
  - Total users, active sessions
  - Job postings and applications
  - Interview schedules
  - System performance metrics

### User Management
- **User Operations**
  - Create, edit, delete users
  - Bulk user operations
  - User role assignment
  - Account activation/deactivation
  - Password reset functionality

### Role & Permission Management
- **Access Control**
  - Create custom roles
  - Assign permissions to roles
  - Role hierarchy management
  - Permission matrix view

### System Settings
- **Configuration Management**
  - Email templates
  - Notification settings
  - System parameters
  - Integration settings
  - Security policies

### Audit & Monitoring
- **System Tracking**
  - User activity logs
  - System access logs
  - Data modification tracking
  - Security event monitoring
  - Performance analytics

## 🔄 CI/CD Pipeline

### GitHub Actions Workflow

\`\`\`yaml
# .github/workflows/ci-cd.yml
name: CI/CD Pipeline

on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main ]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'
          cache: 'npm'
      
      - name: Install dependencies
        run: npm ci
      
      - name: Run linting
        run: npm run lint
      
      - name: Run unit tests
        run: npm run test:coverage
      
      - name: Run e2e tests
        run: npm run e2e

  build:
    needs: test
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'
          cache: 'npm'
      
      - name: Install dependencies
        run: npm ci
      
      - name: Build application
        run: npm run build:prod
      
      - name: Upload build artifacts
        uses: actions/upload-artifact@v3
        with:
          name: dist
          path: dist/

  deploy:
    needs: build
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/main'
    steps:
      - name: Deploy to production
        run: echo "Deploy to production server"
\`\`\`

### Development Workflow

\`\`\`bash
# Development commands
npm start                 # Start development server
npm run build            # Build for production
npm run test             # Run unit tests
npm run test:coverage    # Run tests with coverage
npm run e2e              # Run end-to-end tests
npm run lint             # Run ESLint
npm run format           # Format code with Prettier
npm run analyze          # Analyze bundle size
\`\`\`

## 📊 Complete Feature Summary

### 🔐 Authentication & Security
- ✅ JWT-based authentication
- ✅ Role-based access control (RBAC)
- ✅ Multi-factor authentication ready
- ✅ Session management
- ✅ Password policies
- ✅ Account lockout protection
- ✅ Audit logging
- ✅ XSS and CSRF protection

### 👥 User Management
- ✅ User CRUD operations
- ✅ Bulk user operations
- ✅ User profile management
- ✅ Role assignment
- ✅ Department management
- ✅ User activity tracking

### 💼 Job Management
- ✅ Job posting creation and editing
- ✅ Job categorization and tagging
- ✅ Advanced job search and filtering
- ✅ Job application tracking
- ✅ Application status management
- ✅ Bulk job operations

### 📅 Interview Scheduling
- ✅ Calendar integration
- ✅ Interview slot management
- ✅ Automated notifications
- ✅ Interview feedback collection
- ✅ Reschedule and cancellation
- ✅ Multi-interviewer coordination

### 📄 Document Management
- ✅ Resume upload and parsing
- ✅ Document categorization
- ✅ File security and validation
- ✅ Document versioning
- ✅ Bulk document operations

### 📧 Communication
- ✅ Email notifications
- ✅ SMS notifications (ready)
- ✅ In-app messaging
- ✅ Template management
- ✅ Automated reminders

### 📈 Analytics & Reporting
- ✅ Dashboard analytics
- ✅ Custom report generation
- ✅ Data visualization
- ✅ Export functionality
- ✅ Performance metrics

### 🎨 UI/UX Features
- ✅ Responsive design
- ✅ Dark/light theme support
- ✅ Accessibility compliance (WCAG)
- ✅ Progressive Web App (PWA)
- ✅ Offline support ready
- ✅ Mobile-first design

### ⚡ Performance Features
- ✅ Lazy loading modules
- ✅ Virtual scrolling
- ✅ Caching strategies
- ✅ Bundle optimization
- ✅ Service worker support
- ✅ CDN ready

## 🚀 Deployment

### Production Build
\`\`\`bash
# Build for production
npm run build:prod

# Serve production build locally
npm run serve:prod
\`\`\`

### Environment Configuration
\`\`\`typescript
// environment.prod.ts
export const environment = {
  production: true,
  apiUrl: 'https://api.yourcompany.com',
  enableAnalytics: true,
  enableServiceWorker: true,
  cacheTimeout: 300000, // 5 minutes
};
\`\`\`

### Docker Deployment
\`\`\`dockerfile
# Dockerfile
FROM node:18-alpine as build
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build:prod

FROM nginx:alpine
COPY --from=build /app/dist /usr/share/nginx/html
COPY nginx.conf /etc/nginx/nginx.conf
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
\`\`\`

## 🧪 Testing

### Unit Testing
\`\`\`bash
# Run unit tests
npm run test

# Run tests with coverage
npm run test:coverage

# Run tests in watch mode
npm run test:watch
\`\`\`

### E2E Testing
\`\`\`bash
# Run e2e tests
npm run e2e

# Run e2e tests in headless mode
npm run e2e:headless
\`\`\`

## 📚 Documentation

### API Documentation
- Swagger/OpenAPI documentation available at `/api/docs`
- Postman collection included in `/docs/postman/`

### Component Documentation
- Storybook documentation: `npm run storybook`
- Component examples and usage guidelines

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/new-feature`
3. Commit changes: `git commit -am 'Add new feature'`
4. Push to branch: `git push origin feature/new-feature`
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

For support and questions:
- Create an issue on GitHub
- Contact the development team
- Check the documentation wiki

## 🔄 Version History

- **v2.0.0** - Complete rewrite with Angular 17, enhanced security, and modern UI
- **v1.5.0** - Added interview scheduling and calendar integration
- **v1.0.0** - Initial release with basic HR management features

---

**Built with ❤️ using Angular 17, TypeScript, and modern web technologies.**
