# prisma
Estudando Prisma.io

## Clone this repo
```git@github.com:wellpinho/prisma.git```

## after cloned use
```yarn```

## 1: run project
```yarn dev```

## 2: Prisma Studio
*prism studio is a tool that helps to visualize models and database tables*
```yarn prisma studio```

## 3: access the url
*http://localhost:5555/

## Docker install on Ubuntu 21.04
*Remove old version*
```sudo apt-get remove docker docker-engine docker.io containerd runc```

*Update packages*
```sudo apt-get update```
```sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```
```curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -```
```sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```
```sudo apt-get update```

*Docker Engine install*
```sudo apt-get install docker-ce docker-ce-cli containerd.io```

*Test if Docker is installed*
```sudo docker run hello-world```

*Insert user on Docker*
```sudo usermod -aG docker $USER```

*Start Docker*
```sudo systemctl start docker.service```

*Create a container*
```docker run -p 5432:5432 --name your-db-name -e POSTGRES_PASSWORD=your-db-password -d postgres```

*Start and stop a container docker*
```
  docker container start ID_DO_CONTAINER
  docker container stop ID_DO_CONTAINER
```
*Remove a container id*
```docker container rm ID_DO_CONTAINER```

## Prisma Client
*Models example*
```
model Modules {
  id          String   @id @default(uuid())
  name        String   @unique
  description String
  created_at  DateTime @default(now())

  @@map("modules")
}
```
*create data table*
```yarn prisma migrate dev```
*model generate*
```yarn prisma generate```
