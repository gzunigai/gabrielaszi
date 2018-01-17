# gabrielaszi

import PyQt4.QtGui as qt
import PyQt4.QtCore as qtc

class ClientWindow(qt.QWidget):
    def __init__(self,parent=None):
        super(ClientWindow,self).__init__(parent)

        self.resize(320, 120)
        self.setWindowTitle("Welcome to your client space")

class WelcomeWindow(qt.QWidget):
    def __init__(self,parent=None):
        super(WelcomeWindow,self).__init__(parent)
@ -30,12 +37,17 @@ class WelcomeWindow(qt.QWidget):
        btnClient.pressed.connect(self.userIsClient)
        btnEmployee.pressed.connect(self.userIsEmployee)

        self.clientWindow= ClientWindow()

        mainBox.addLayout(titleBox)
        mainBox.addLayout(buttonsBox)
        self.setLayout(mainBox)



    def userIsClient(self):
        print('client')
        self.clientWindow.show()

    def userIsAdmin(self):
        print('admin')
