FROM php:8.4-apache

# Instalar dependencias del sistema
RUN apt-get update && apt-get install -y \
    git \
    nano \
    unzip \
    curl \
    sudo \
    libpq-dev \
    libpng-dev \
    libjpeg-dev \
    libfreetype6-dev \
    libxml2-dev \
    libsodium-dev \
    libzip-dev \
    zlib1g-dev \
    libonig-dev \
    libcurl4-openssl-dev \
    libbz2-dev \
    libsqlite3-dev \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install -j$(nproc) \
        gd \
        soap \
        sodium \
        pdo \
        pdo_mysql \
        pdo_sqlite \
        mysqli \
        bz2 \
        curl \
        mbstring \
        gettext \
        fileinfo \
        exif \
        zip \
        opcache \
    && docker-php-ext-enable opcache


# Habilitar mod_rewrite (útil para Symfony, Laravel, etc.)
RUN a2enmod rewrite

# Instalar Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Configurar directorio de trabajo
WORKDIR /var/www/html

# No es necesario si no uso imagenes
# Copiar archivos de la aplicación
# COPY . /var/www/html

# Node.js 24, LTS actual (Krypton). Soporte hasta abril de 2028.
RUN curl -fsSL https://deb.nodesource.com/setup_24.x | bash - && \
    apt-get install -y nodejs

COPY docker/apache2/000-default.conf /etc/apache2/sites-available/000-default.conf

# Copiar entrypoint
# COPY docker/entrypoint.sh /entrypoint.sh
# RUN chmod +x /entrypoint.sh

# ENTRYPOINT ["/entrypoint.sh"]
CMD ["apache2-foreground"]

EXPOSE 80
