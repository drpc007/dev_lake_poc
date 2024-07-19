# poc-devlake

# Apache DevLake Installation Guide

This guide provides instructions on how to install and use Apache DevLake using Docker Compose.

## Prerequisites

Before you begin, ensure you have Docker and Docker Compose installed on your system.

## Installation Steps

1. **Download Required Files**: Download the following files from the [Apache DevLake Release Page](https://github.com/apache/incubator-devlake/releases/tag/v1.0.0):
   - `docker-compose.yml`
   - `env.example`

2. **Rename the Environment File**: Rename `env.example` to `.env` using the command:
   ```bash
   mv env.example .env

3. **Generate a Secure Encryption Key:**:  Use OpenSSL to generate a secure encryption key. Run the following command to generate a 128-character string consisting of uppercase letters:
   ```bash
   openssl rand -base64 2000 | tr -dc 'A-Z' | fold -w 128 | head -n 1

4. **Set the Encryption Key:**: set the ENCRYPTION_SECRET environment variable in the .env file: ENCRYPTION_SECRET="copied string"

5. **Start Docker Compose:**: 
   ```bash
   docker-compose up -d

This command will launch 4 containers as specified in the docker-compose.yml file:

MySQL
Grafana
DevLake Core
DevLake Config UI

4. **Access the Config UI**:  Open your web browser and navigate to http://localhost:4000/ to view the Config UI and start configuring Apache DevLake.






