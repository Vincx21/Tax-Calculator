from PyQt5.QtWidgets import (
    QApplication, QWidget, QFormLayout, QPushButton, QLabel, QLineEdit
)

def calculate(result_tax, agi, nti, result_ti):
    a = 50000000
    b = 250000000
    c = 500000000
    if agi and nti:
        if agi.isnumeric() and nti.isnumeric(): 
            ti = float(agi) - float(nti)
            result_ti.setText(str(ti))
            if ti <= a: 
                tax = ti * 0.05
                result_tax.setText(str(tax))
            elif ti <= b:
                tax = 0.05 * a + (ti - a) * 0.15
                result_tax.setText(str(tax))
            elif ti <= c:
                tax = (0.05 * a) + (0.15 * (b - a)) + (ti - b) * 0.25
                result_tax.setText(str(tax))
            else:
                tax = (0.05 * a) + (0.15 * (b - a)) + (0.25 * b) + (ti - c) * 0.3
                result_tax.setText(str(tax))
        else:
            result_tax.setText("Please enter a number!")

def main():
    app = QApplication([])
    window = QWidget()
    window.setWindowTitle("Tax Calculator")

    form_layout = QFormLayout()
    label_agi = QLabel('Enter AGI(Annual Gross Income)')
    label_nti = QLabel('Enter NTI(Non-Taxable Income)')
    label_ti = QLabel('Taxable Income: ')
    result_ti = QLabel()
    label_tax = QLabel('Tax: ')
    result_tax = QLabel()

    agi_input = QLineEdit()
    nti_input = QLineEdit()

    button_calculate = QPushButton('Calculate')

    button_calculate.clicked.connect(
        lambda: calculate(result_tax, agi_input.text(), nti_input.text(), result_ti)
    )

    form_layout.addRow(label_agi, agi_input)
    form_layout.addRow(label_nti, nti_input)
    form_layout.addRow(button_calculate)
    form_layout.addRow(label_ti, result_ti)
    form_layout.addRow(label_tax, result_tax)

    button_save = QPushButton('Save')

    button_save.clicked.connect()

    window.setLayout(form_layout)
    window.show()
    app.exec_()

main()
