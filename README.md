
## 1\. JavaScript网页设计案例


下面我将提供一个简单的JavaScript网页设计案例，该案例将实现一个动态的待办事项列表（Todo List）。用户可以在页面上添加新的待办事项，标记它们为已完成，以及删除它们。这个案例将使用HTML来构建页面结构，CSS来美化页面，以及JavaScript来添加动态功能。


### 1\.1 HTML (index.html)



```
html>  
<html lang="en">  
<head>  
    <meta charset="UTF-8">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>Todo Listtitle>  
    <link rel="stylesheet" href="style.css">  
head>  
<body>  
    <h1>Todo Listh1>  
    <input type="text" id="todoInput" placeholder="Add new todo...">  
    <button onclick="addTodo()">Add Todobutton>  
    <ul id="todoList">  
          
    ul>  
  
    <script src="script.js">script>  
body>  
html>

```

### 1\.2 CSS (style.css)



```
body {  
    font-family: Arial, sans-serif;  
    margin: 20px;  
    padding: 0;  
}  
  
#todoList {  
    list-style-type: none;  
    padding: 0;  
}  
  
#todoList li {  
    margin: 10px 0;  
    padding: 10px;  
    background-color: #f4f4f4;  
    border: 1px solid #ddd;  
    display: flex;  
    align-items: center;  
    justify-content: space-between;  
}  
  
#todoList li.completed {  
    text-decoration: line-through;  
    opacity: 0.5;  
}  
  
#todoInput {  
    padding: 10px;  
    margin-right: 10px;  
    width: calc(100% - 120px);  
}  
  
button {  
    padding: 10px 20px;  
    cursor: pointer;  
}

```

### 1\.3 JavaScript (script.js)



```
function addTodo() {  
    const input = document.getElementById('todoInput');  
    const list = document.getElementById('todoList');  
    const itemText = input.value.trim();  
  
    if (itemText) {  
        const itemElement = document.createElement('li');  
        itemElement.textContent = itemText;  
  
        // Checkbox for marking todo as completed  
        const checkbox = document.createElement('input');  
        checkbox.type = 'checkbox';  
        checkbox.onclick = function() {  
            itemElement.classList.toggle('completed', this.checked);  
        };  
  
        // Button for deleting todo  
        const deleteButton = document.createElement('button');  
        deleteButton.textContent = 'Delete';  
        deleteButton.onclick = function() {  
            list.removeChild(itemElement);  
        };  
  
        // Append elements to the list item  
        itemElement.appendChild(checkbox);  
        itemElement.appendChild(document.createTextNode('\u00A0')); // Add space  
        itemElement.appendChild(deleteButton);  
  
        // Append list item to the list  
        list.appendChild(itemElement);  
  
        // Clear input field  
        input.value = '';  
    }  
}  
  
// Optionally, add event listener to input field for Enter key press  
document.getElementById('todoInput').addEventListener('keypress', function(event) {  
    if (event.key === 'Enter') {  
        addTodo();  
    }  
});

```

### 1\.4说明


（1）**HTML** 部分定义了页面的基本结构，包括一个输入框用于输入待办事项，一个按钮用于添加待办事项，以及一个无序列表用于显示待办事项。


（2）**CSS** 部分美化了页面，包括待办事项列表的样式、输入框和按钮的样式。


（3）**JavaScript** 部分实现了动态功能：


* 监听“添加待办事项”按钮的点击事件，并调用 `addTodo` 函数。
* `addTodo` 函数从输入框中获取文本，创建一个新的列表项，并为其添加复选框和删除按钮。
* 复选框用于标记待办事项为已完成，点击时切换列表项的样式。
* 删除按钮用于从列表中删除待办事项。
* 监听输入框的 `keypress` 事件，以便在按下 Enter 键时也能添加待办事项。


这个案例展示了如何使用HTML、CSS和JavaScript来创建一个具有基本动态功能的网页应用。


## 2\. JavaScript网页设计案例不同的功能和设计思路展示


除了上述的待办事项列表案例外，还有许多其他类似的JavaScript网页设计案例，这些案例展示了不同的功能和设计思路。以下是一些常见的案例及其简要描述：


### 2\.1 图片画廊（Image Gallery）


（1）**功能描述**：


* 展示一组图片，并支持点击放大查看。
* 使用HTML和CSS创建图片网格布局。
* 使用JavaScript处理图片点击事件，显示放大的图片。


（2）**代码示例**（简化版）：



```
html>  
<html lang="en">  
<head>  
    <meta charset="UTF-8">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>Image Gallerytitle>  
    <style>  
        .gallery img {  
            width: 100px; /* 或其他尺寸 */  
            height: auto;  
            margin: 10px;  
            cursor: pointer;  
        }  
        .modal {  
            display: none;  
            position: fixed;  
            z-index: 1;  
            /* 其他模态框样式 */  
        }  
        .modal-content {  
            /* 放大图片的样式 */  
        }  
    style>  
head>  
<body>  
  
<div class="gallery">  
    <img src="image1.jpg" alt="Image 1">  
    <img src="image2.jpg" alt="Image 2">  
      
div>  
  
<div id="modal" class="modal">  
    <span class="close">&times;span>  
    <img class="modal-content" id="modalImg">  
div>  
  
<script>  
    // JavaScript 代码，用于处理点击事件和显示模态框  
    // ...（省略详细实现）  
script>  
  
body>  
html>

```

### 2\.2 简易天气应用（Weather App）


（1）**功能描述**：


* 获取并显示天气信息。
* 使用天气API（如OpenWeatherMap）获取实时天气数据。
* 使用JavaScript动态更新页面内容。


（2）**代码示例**（简化版，需要替换API密钥）：



```
html>  
<html lang="en">  
<head>  
    <meta charset="UTF-8">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>Weather Apptitle>  
head>  
<body>  
  
<h1>Weather Apph1>  
<input type="text" id="cityInput" placeholder="Enter city">  
<button id="getWeather">Get Weatherbutton>  
<div id="weatherResult">div>  
  
<script>  
    const apiKey = 'YOUR_API_KEY'; // 替换为你的API密钥  
  
    document.getElementById('getWeather').onclick = function() {  
        const city = document.getElementById('cityInput').value;  
        fetch(`https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}&units=metric`)  
            .then(response => response.json())  
            .then(data => {  
                const temp = data.main.temp;  
                const weatherDescription = data.weather[0].description;  
                document.getElementById('weatherResult').innerHTML = `Temperature: ${temp}°CDescription: ${weatherDescription}`;  
            })  
            .catch(error => {  
                document.getElementById('weatherResult').innerHTML = 'City not found.';  
            });  
    };  
script>  
  
body>  
html>

```

### 2\.3 动态表格（Dynamic Table）


（1）**功能描述**：


* 展示一个表格，表格内容可以动态添加、删除或修改。
* 使用HTML创建表格结构。
* 使用JavaScript处理数据的增删改操作，并动态更新表格内容。


（2）**代码示例**（由于篇幅限制，仅提供概念性描述）：


* 创建一个HTML表格，包含表头和若干行。
* 使用JavaScript添加按钮或输入框，以便用户输入新数据。
* 编写JavaScript函数来处理添加、删除和修改数据的逻辑。
* 使用DOM操作动态更新表格内容。


这些案例涵盖了网页设计的不同方面，从基本的图片展示到实用的天气查询，再到动态的数据处理。它们都是学习JavaScript网页开发的良好起点，并可以根据实际需求进行扩展和定制。


 本博客参考[悠兔机场](https://xinnongbo.com)。转载请注明出处！
