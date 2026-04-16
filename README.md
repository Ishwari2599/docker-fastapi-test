# docker-fastapi-test (Deployed on AWS EC2)

## 📌 Project Overview

This project demonstrates how to containerize a FastAPI application using Docker and run it using docker-compose. The application is deployed and tested on an AWS EC2 instance with persistent data storage.

---

## 🛠️ Tech Stack

* FastAPI
* Docker
* Docker Compose
* AWS EC2

---

## 📂 Project Structure

```
docker-fastapi-test/
 ├── app/
 │    ├── main.py
 │    ├── services.py
 │    ├── schema.py
 ├── data/
 ├── Dockerfile
 ├── docker-compose.yml
 ├── requirements.txt
```

---

## ⚙️ Setup & Run (EC2)

### 1️⃣ Launch EC2 Instance

* Create Ubuntu instance on AWS
* Open ports:

  * 22 (SSH)
  * 8000 (Application)

---

### 2️⃣ Connect to EC2

```
ssh -i your-key.pem ubuntu@<your-ec2-public-ip>
```

---

### 3️⃣ Install Dependencies

```
sudo apt update
sudo apt install docker.io -y
sudo apt install docker-compose -y
sudo apt install git -y
```

---

### 4️⃣ Clone Repository

```
git clone https://github.com/YOUR_USERNAME/docker-fastapi-test.git
cd docker-fastapi-test
```

---

### 5️⃣ Run Application

```
sudo docker compose up --build
```

---

## 🌐 Access API

Open in browser:

```
http://<your-ec2-public-ip>:8000/docs
```

---

## 📌 API Endpoints

### 🔹 GET /

Returns welcome message

### 🔹 GET /users

Returns list of users

### 🔹 POST /users

Adds new user

Example request:

```
{
  "first_name": "Ishwari",
  "last_name": "Tajane",
   "age" : 22
}
```

---

## 💾 Data Persistence

* Data is stored in `users.json`
* Docker volume mapping is used:

```
./data:/app/app/data
```

* Ensures data remains even after container restart

---

## 🔁 Persistence Test

```
sudo docker compose down
sudo docker compose up
```

✔ Data remains intact after restart

---

## ✅ Features

* FastAPI REST API
* Dockerized application
* Docker Compose setup
* Persistent storage using volumes
* Deployed on AWS EC2

---

## 📬 Conclusion

This project successfully demonstrates containerization, deployment, and data persistence using Docker and AWS EC2.

---
