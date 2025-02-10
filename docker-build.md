# Construire l'image
docker build -t mon-image:tag .

# Voir les images
docker images

# Lancer un conteneur
docker run -p 3000:3000 mon-image:tag

# Taguer l'image pour un registry
docker tag mon-image:tag username/mon-image:tag

# Pousser l'image
docker push username/mon-image:tag

# Docker run database.
docker run -p "5432:5432" -d -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=Desire01 --name pg_database postgres:15-alpine

# Docker exec database deploy.
docker exec agendax_api npx run db:pull