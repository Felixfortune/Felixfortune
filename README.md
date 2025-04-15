# 📡 Server Monitoring & Self-Healing Tool

A lightweight Python-based tool to monitor system health, detect service downtimes, and automatically recover from failures with real-time alerts and a web dashboard.

---

## 🔧 Features

- ✅ **Database Monitoring** – Check if MySQL is running and reconnect/restart if needed.
- 🌐 **URL Health Check** – Verify if your service is accessible online.
- 💽 **Disk Usage Alerts** – Notify when disk usage exceeds threshold.
- 🔁 **Self-Healing** – Automatically restart failed services.
- 📨 **Email Notifications** – Get notified when errors are detected or users log in.
- 🔐 **Web Dashboard** – Access system stats via a password-protected Flask dashboard.

---

## ⚙️ Deployment Instructions

1. **Clone the repo and navigate into it**

```bash
cd ~/servermon
```

2. **Set up your virtual environment and activate**

```bash
python3 -m venv servermon-env
source servermon-env/bin/activate
```

3. **Install dependencies**

```bash
pip install flask psutil mysql-connector-python requests
```

4. \*\*Add Email Credentials in \*\***`self_heal.py`**

```python
EMAIL = "felixfortune80@gmail.com"
APP_PASSWORD = "yyzk dith niun pjxv"
```

5. **Set up Cron Jobs**

```cron
*/10 * * * * /home/lixtune/servermon/servermon-env/bin/python3 /home/lixtune/servermon/self_heal.py >> /home/lixtune/servermon/self_heal.log 2>&1
```

6. **Run the Dashboard**

```bash
python dashboard_server.py
```

Then open [http://192.168.1.107:3001/dashboard](http://192.168.1.107:3001/dashboard)

- Username: `lixtune`
- Password: `admin`

---

## 📁 Project Structure

```
servermon/
├── dashboard_server.py
├── self_heal.py
├── servermon-env/
└── ...
```

---

## 🧠 How It Works

- The script `self_heal.py` runs every 10 minutes to check for system health.
- If MySQL is down, it attempts to restart it.
- On login to the dashboard, you’ll get an email alert with the IP of the user who logged in.

---

## 🚀 Author

Built with ❤️ by Felix .F Mukabana (Lixtune)

> Simple. Smart. Self-healing.

