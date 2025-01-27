FROM php:8.2-fpm

# Install system dependencies
RUN apt-get update && apt-get install -y \
    git \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    unzip \
    gnupg2 \
    ca-certificates \
    lsb-release

# Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Install PHP extensions
RUN docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath gd

# Install Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Install Node.js and npm
RUN curl -fsSL https://deb.nodesource.com/setup_18.x | bash - \
    && apt-get install -y nodejs \
    && npm install -g npm

# Set working directory
WORKDIR /var/www/html

# Install Laravel and Livewire
RUN composer create-project --prefer-dist laravel/laravel .
RUN composer require livewire/livewire

# Optionally install Node.js dependencies (package.json must exist)
# COPY package*.json ./
# RUN npm install

# Expose the web port
EXPOSE 9000
