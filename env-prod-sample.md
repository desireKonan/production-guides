# Env prod sample.

Voici un exemple de fichier d'environnement a utiliser en production. Ce fichier est a utiliser pour la prod (a mettre sur le serveur de prod).

```

NODE_ENV=production

PORT=3005

DATABASE_URL="postgresql://postgres:Desire01@172.17.0.1:5432/agendax?schema=public&connect_timeout=10000&connection_limit=15"

# SMTP Configuration (Mailpit)
SMTP_HOST=smtp.hostinger.com
SMTP_PORT=465
SMTP_USER=no-reply@agendax-events.com
SMTP_PASS=Matadores12@S.12

# Sender Configuration
FROM_NAME=AGENDAX
FROM_EMAIL=noreply@agendax.com

AGENDAX_PAYMENT_URL="https://www.pay.moneyfusion.net/Agendax/6aba1e5820821fae/pay/"

REDIRECTION_URL="https://site.agendax-ci.com/buy/:id"

JWT_SECRET="eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36P>

EXPIRE_DAYS="2d"

CORS_ORIGINS=https://site.agendax-ci.com,https://admin.agendax-ci.com

```