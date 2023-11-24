# webdevtask1
landing page
html code-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title> Calculator </title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background: linear-gradient(45deg, #0a0a0a, #3a4452);
        }

        #calculator {
            background-color: transparent;
            border-radius: 8px;
            box-shadow: 0 0 15px #000;
            border: 2px solid rgb(116, 114, 114);
            padding: 20px;
            width: 360px;
        }

        #display {
            color: #fff;
        }

        input[type="text"] {
            width: 90%;
            margin-bottom: 10px;
            padding: 20px;
            font-size: 40px;
            border: 1px solid #fff;
            border-radius: 4px;
            text-align: right;
            cursor: pointer;
            background: transparent;
        }

        input::placeholder {
            color: #fff;
        }

        table {
            width: 360px;
        }

        table tr td {
            padding: 10px;
            text-align: center;
        }

        table tr td button {
            width: 70px;
            height: 70px;
            padding: 10px;
            font-size: 22px;
            font-weight: 600;
            border-radius: 10px;
            cursor: pointer;
            box-shadow: -5px -6px 15px #000;
            background: transparent;
            color: #fff;
            outline: 1px solid #313131;
            outline-offset: 3px;
        }

        button:active {
            background: #000;
            transform: translate(2px, 2px);
        }

        table tr td button.operator {
            color: #fbff00;
            background: #1e1919;
            font-weight: 700;
        }

        table tr td button.equal {
            background-color: orangered;
            font-weight: 900;
            color: #fff;
        }
    </style>
</head>
<body>
<div id="calculator">
    <input type="text" id="display" value="0" placeholder="0" disabled>

    <table>
        <tr>
            <td><button class="operator">AC</button></td>
            <td><button class="operator">DEL</button></td>
            <td><button class="operator">%</button></td>
            <td><button class="operator">/</button></td>
        </tr>
        <tr>
            <td><button>7</button></td>
            <td><button>8</button></td>
            <td><button>9</button></td>
            <td><button class="operator">*</button></td>
        </tr>
        <tr>
            <td><button>4</button></td>
            <td><button>5</button></td>
            <td><button>6</button></td>
            <td><button class="operator">+</button></td>
        </tr>
        <tr>
            <td><button>1</button></td>
            <td><button>2</button></td>
            <td><button>3</button></td>
            <td><button class="operator">-</button></td>
        </tr>
        <tr>
            <td><button>00</button></td>
            <td><button>0</button></td>
            <td><button>.</button></td>
            <td><button class="equal">=</button></td>
        </tr>
    </table>
</div>

<script>
    document.addEventListener("DOMContentLoaded", function () {
        const display = document.getElementById('display');
        const buttons = document.querySelectorAll('button');

        buttons.forEach(button => {
            button.addEventListener('click', function () {
                const buttonText = button.textContent;

                switch (buttonText) {
                    case 'AC':
                        display.value = '';
                        break;
                    case 'DEL':
                        display.value = display.value.slice(0, -1);
                        break;
                    case '+/-':
                        display.value = eval(display.value) * -1;
                        break;
                    case '=':
                        display.value = eval(display.value);
                        break;
                    default:
                        display.value += buttonText;
                        break;
                }
            });
        });
    });
</script>
</body>
</html>
