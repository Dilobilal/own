# 1. Node.js-Image verwenden
FROM node:16-alpine

# 2. Arbeitsverzeichnis setzen
WORKDIR /app

# 3. Kopiere die package.json und package-lock.json
COPY package*.json ./

# 4. Installiere die Abhängigkeiten
RUN npm install

# 5. Kopiere alle Dateien in den Container
COPY . .

# 6. Installiere `serve` global
RUN npm install -g serve

# 7. Führe den Server im Verzeichnis `/app` (entspricht `bmbf-fe`) aus
CMD ["serve", "-s", "dist", "-l", "8080"]

# 8. Öffne den Port 8080
EXPOSE 8080