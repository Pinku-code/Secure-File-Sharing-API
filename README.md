# Secure File Sharing - API

### Features

#### Technology Stack
- **Framework**: Flask
- **Database**: MongoDB
- **Authentication**: JWT (JSON Web Tokens)
- **File Type Detection**: python-magic
  - The file type is determined not only by the file extension but also by analyzing its contents.
<hr>

### API Endpoints
#### Authentication
- **POST** `/signup`: Sign up a new user
- **GET** `/verify-email/<token>`: Verify user's email
- **POST** `/login`: Log in a user

#### File Operations
- **POST** `/upload`: Upload a file (Operation Users only)
- **GET** `/files`: List all uploaded files
- **GET** `/download/<file_id>`: Generate a download link for a file
- **GET** `/secure-download/<token>`: Download a file using a secure token
<hr>

### Setup and Installation
Make sure you are using `Python 3.12` or later. <br>
These instructions will help you get set up with a local development environment
1. Clone the repository:
   ```shell
   git clone https://github.com/Pinku-code/Secure-File-Sharing-API.git
   cd Secure-File-Sharing-API
   ```
2. Set up a virtual environment:
   ```shell
   python -m venv venv
   ./venv/Scripts/activate  # On Linux use `source venv\bin\activate`
   ```
3. Install dependencies:
   ```shell
   pip install -r requirements.txt
   pip install python-magic-bin~=0.4.14 # only for Windows 
   sudo apt update && sudo apt install -y libmagic-dev # only for Linux
   ```
4. Set up environment variables:<br>
   Create a `.env` file in the root directory and add the following:
   ```
   SECRET_KEY=your_secret_key
   MONGO_URI=your_mongodb_uri
   UPLOAD_FOLDER=path_to_upload_folder
   SMTP2GO_API_KEY=your_smtp2go_api_key
   SMTP2GO_SENDER='sender_name <sender_email>'
   BASE_URL='' # specify the base URL of your application or leave empty for 127.0.0.1:5000
   ```
5. Run the application:
   ```shell
   python run.py
   ```
<hr>

### Access your application <br>
The application should now be accessible at `http://localhost:5000`
<hr>

### License
MIT License
