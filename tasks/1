import sys
import random
from PyQt6 import QtWidgets
int_rand = random.randint(1, 100)
attemps = 5
def clickButton():
    global attemps
    global int_rand
    attemps -= 1
    inp_num = int(input_text.text())
    if (inp_num == int_rand):
        result.setText("<center>Вы угадали, ура!</center>")
        label.hide()
        input_text.hide()
        btnSend.hide()
    else:
        att_txt = str(attemps)
        intr_txt = str(int_rand)
        if inp_num > int_rand:
            hint = "больше"
        else:
            hint = "меньше"
        if attemps > 0:
            result.setText("Вы не угадали. Осталось попыток: "+att_txt+"<br><b>Подсказка:</b> Вы указали число "+hint+" нужного")
        else:
            result.setText("Вы не угадали и проиграли. Было число "+intr_txt+". Начать заново?")
            label.hide()
            input_text.hide()
            btnSend.hide()
            btnRetry.show()
            btnQuit.show()
    input_text.setText("")
    result.show()
def retryButton():
    global attemps
    attemps = 5
    int_rand = random.randint(1, 100)
    result.hide()
    btnRetry.hide()
    btnQuit.hide()
    label.show()
    input_text.show()
    btnSend.show()
app = QtWidgets.QApplication(sys.argv)
window = QtWidgets.QWidget()
window.setWindowTitle("Игра")
window.resize(300, 70)
label = QtWidgets.QLabel("<center>Привет! Угадай число от 1 до 100</center>")
input_text = QtWidgets.QLineEdit()
btnSend = QtWidgets.QPushButton("Отправить")
btnRetry = QtWidgets.QPushButton("Начать заново")
btnQuit = QtWidgets.QPushButton("Закрыть")
result = QtWidgets.QLabel("")
vbox = QtWidgets.QVBoxLayout()
vbox.addWidget(label)
vbox.addWidget(input_text)
vbox.addWidget(btnSend)
vbox.addWidget(result)
vbox.addWidget(btnRetry)
vbox.addWidget(btnQuit)
result.hide()
btnRetry.hide()
btnQuit.hide()
window.setLayout(vbox)
btnSend.clicked.connect(clickButton)
btnRetry.clicked.connect(retryButton)
btnQuit.clicked.connect(app.quit)
window.show()
sys.exit(app.exec())
