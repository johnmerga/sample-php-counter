# Laravel Livewire Docker Project

## Prerequisites

- Docker
- Docker Compose

## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/johnmerga/sample-php-counter.git
cd sample-php-counter
```

### 2. Start Containers

```bash
docker-compose up -d --build
```

### 3. Install Dependencies

```bash
docker-compose exec php composer install
docker-compose exec php php artisan key:generate
```

### 4. Access the Application

- Website: http://localhost
- MySQL:
  - Host: localhost
  - Port: 3306
  - Database: laravel
  - User: laravel
  - Password: laravel

## Common Commands

```bash
# Stop containers
docker-compose down

# Rebuild containers
docker-compose up -d --build

# Access PHP container
docker-compose exec php bash
```

## Livewire Component

A sample Counter component is pre-configured in:

- `app/Livewire/Counter.php`
- `resources/views/livewire/counter.blade.php`

## Troubleshooting

- Ensure all ports (80, 3306) are available
- Check Docker and Docker Compose versions
