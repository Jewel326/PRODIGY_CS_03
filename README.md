# PRODIGY_CS_03
Building a password complexity checker.

This is a simple web-based tool that evaluates the strength of a password based on various criteria, such as length, the presence of uppercase and lowercase letters, numbers, and special characters. The tool provides instant feedback on the strength of the entered password, categorizing it as "Strong", "Moderate", or "Weak."

## Features
- Real-time feedback on password strength.
- Checks for password length (minimum 8 characters).
- Checks for the presence of:
  - Uppercase letters (A-Z)
  - Lowercase letters (a-z)
  - Numbers (0-9)
  - Special characters (`!@#$%^&*(),.?":{}|<>`)
- Color-coded feedback for easy understanding:
  - Green: Strong password
  - Orange: Moderate password
  - Red: Weak password

## Demo
You can see the live demo of the password checker by opening the `index.html` file in your browser.

## Installation
### Step 1: Clone the Repository
To clone this repository, use the following command in your terminal:

```bash
git clone https://github.com/Jewel326/password-complexity-checker.git
```

### Step 2: Navigate to the Project Directory
Once the repository is cloned, navigate to the project directory:

```bash
cd password-complexity-checker
```

### Step 3: Open the `index.html` File
Open the `index.html` file in your web browser to use the Password Complexity Checker:

- Double-click the `index.html` file, or
- Run a simple local server and open the file in a browser.

### Optional: Serve Using Python HTTP Server
To serve the project using Python (optional):

```bash
python3 -m http.server
```

Navigate to `http://localhost:8000` in your browser.

## Usage
1. Open the Password Complexity Checker in a browser.
2. Type a password in the input field.
3. Observe the real-time feedback below the input field:
   - **Weak password**: If fewer than 3 criteria are met.
   - **Moderate password**: If 3 or 4 criteria are met.
   - **Strong password**: If all 5 criteria are met.

## Example Code
Here's a quick look at the main logic behind the password checker:

```javascript
function checkPassword() {
    const password = document.getElementById('password').value;
    const feedback = document.getElementById('feedback');

    // Define criteria
    const lengthCriteria = password.length >= 8;
    const uppercaseCriteria = /[A-Z]/.test(password);
    const lowercaseCriteria = /[a-z]/.test(password);
    const numberCriteria = /[0-9]/.test(password);
    const specialCriteria = /[!@#$%^&*(),.?":{}|<>]/.test(password);

    // Calculate score
    let strengthScore = 0;
    if (lengthCriteria) strengthScore++;
    if (uppercaseCriteria) strengthScore++;
    if (lowercaseCriteria) strengthScore++;
    if (numberCriteria) strengthScore++;
    if (specialCriteria) strengthScore++;

    // Provide feedback
    if (strengthScore === 5) {
        feedback.textContent = "Strong password";
        feedback.className = "feedback strong";
    } else if (strengthScore >= 3) {
        feedback.textContent = "Moderate password";
        feedback.className = "feedback moderate";
    } else {
        feedback.textContent = "Weak password";
        feedback.className = "feedback weak";
    }
}
```
For this **Password Complexity Checker** project, the following technologies are used:

### 1. **HTML**
   - **Purpose**: Structure and content of the web page.
   - **Usage**: The `index.html` file contains the main elements of the Password Complexity Checker, such as the input field for entering the password, and a section for displaying the feedback.
   
### 2. **CSS**
   - **Purpose**: Styling and layout of the web page.
   - **Usage**:  The `style` tag within the `index.html` provides styles to display feedback to users and makes the checker visually engaging (e.g., color-coded feedback for weak, moderate, and strong passwords).

### 3. **JavaScript**
   - **Purpose**: Adding interactivity and dynamic behavior to the web page.
   - **Usage**: The password strength evaluation is handled entirely using JavaScript. It checks the password input in real-time and provides instant feedback by applying rules such as length, uppercase, lowercase, numbers, and special characters.

### 4. **Git**
   - **Purpose**: Version control for tracking changes in the project files.
   - **Usage**: Git was used to commit changes and push the project to a GitHub repository.

### 5. **GitHub**
   - **Purpose**: Remote repository hosting and collaboration platform.
   - **Usage**: GitHub is used to host the project's source code, making it publicly accessible and allowing others to contribute or clone the project.

## Contributing
Feel free to open a pull request to contribute to this project. Whether it's fixing bugs, improving performance, or adding new features, all contributions are welcome!

