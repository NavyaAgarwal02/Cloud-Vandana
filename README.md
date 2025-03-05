# CloudVandana Assignments Code

## 1. Simple Profile Card

### Description
A responsive profile card using HTML and CSS. The card includes:
- A profile picture
- Name and designation
- A short bio
- Social media icons
- Centered display with responsive design
- Hover effect with CSS animations

### Code
#### `profile-card.html`
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Profile Card</title>
    <link rel="stylesheet" href="profile-card.css">
</head>
<body>
    <div class="profile-card">
        <img src="profile.jpg" alt="Profile Picture" class="profile-pic">
        <h2>John Doe</h2>
        <p>Software Engineer</p>
        <p class="bio">Passionate about web development and design.</p>
        <div class="social-icons">
            <a href="#">🐦</a>
            <a href="#">📘</a>
            <a href="#">📸</a>
        </div>
    </div>
</body>
</html>
```

#### `profile-card.css`
```css
body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background: #f4f4f4;
}

.profile-card {
    text-align: center;
    padding: 20px;
    background: white;
    border-radius: 10px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s;
}

.profile-card:hover {
    transform: scale(1.05);
}

.profile-pic {
    width: 100px;
    border-radius: 50%;
}

.social-icons a {
    margin: 0 5px;
    text-decoration: none;
}
```

---

## 2. String Manipulation - Anagram Check

### Description
Java program to check if two strings are anagrams (same characters, different order).

### Code
#### `AnagramCheck.java`
```java
import java.util.Arrays;
import java.util.Scanner;

public class AnagramCheck {
    public static boolean isAnagram(String str1, String str2) {
        char[] charArray1 = str1.replaceAll("\\s", "").toLowerCase().toCharArray();
        char[] charArray2 = str2.replaceAll("\\s", "").toLowerCase().toCharArray();
        Arrays.sort(charArray1);
        Arrays.sort(charArray2);
        return Arrays.equals(charArray1, charArray2);
    }
    
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter first string: ");
        String str1 = scanner.nextLine();
        System.out.print("Enter second string: ");
        String str2 = scanner.nextLine();
        System.out.println("Are they anagrams? " + isAnagram(str1, str2));
        scanner.close();
    }
}
```

---

## 3. Employee Management System

### Description
A simple Java class `Employee` with attributes and a method to display details.

### Code
#### `Employee.java`
```java
import java.util.ArrayList;
import java.util.List;

class Employee {
    int id;
    String name;
    double salary;
    
    public Employee(int id, String name, double salary) {
        this.id = id;
        this.name = name;
        this.salary = salary;
    }
    
    public void displayDetails() {
        System.out.println("ID: " + id + ", Name: " + name + ", Salary: " + salary);
    }
    
    public static void main(String[] args) {
        List<Employee> employees = new ArrayList<>();
        employees.add(new Employee(1, "Alice", 50000));
        employees.add(new Employee(2, "Bob", 60000));
        employees.add(new Employee(3, "Charlie", 70000));
        
        for (Employee emp : employees) {
            emp.displayDetails();
        }
    }
}
```

---

## 4. To-Do List

### Description
A JavaScript to-do list that allows adding and removing tasks using the DOM.

### Code
#### `todo.html`
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List</title>
</head>
<body>
    <h2>To-Do List</h2>
    <input type="text" id="taskInput" placeholder="Enter task">
    <button onclick="addTask()">Add</button>
    <ul id="taskList"></ul>
    <script src="todo.js"></script>
</body>
</html>
```

#### `todo.js`
```javascript
function addTask() {
    let taskInput = document.getElementById("taskInput");
    let taskList = document.getElementById("taskList");
    if (taskInput.value !== "") {
        let li = document.createElement("li");
        li.textContent = taskInput.value;
        let btn = document.createElement("button");
        btn.textContent = "Remove";
        btn.onclick = function () { taskList.removeChild(li); };
        li.appendChild(btn);
        taskList.appendChild(li);
        taskInput.value = "";
    }
}
```

---

## 5. Image Slider

### Description
A simple JavaScript image slider with next and previous buttons.

### Code
#### `slider.html`
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Slider</title>
</head>
<body>
    <img id="slider" src="image1.jpg" width="500">
    <br>
    <button onclick="prevImage()">Previous</button>
    <button onclick="nextImage()">Next</button>
    <script src="slider.js"></script>
</body>
</html>
```

#### `slider.js`
```javascript
let images = ["image1.jpg", "image2.jpg", "image3.jpg"];
let index = 0;

function nextImage() {
    index = (index + 1) % images.length;
    document.getElementById("slider").src = images[index];
}

function prevImage() {
    index = (index - 1 + images.length) % images.length;
    document.getElementById("slider").src = images[index];
}
```

---

Each assignment is structured for easy GitHub upload with separate files and documentation. Let me know if you need changes!
