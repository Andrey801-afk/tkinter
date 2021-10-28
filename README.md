# tkinter
from tkinter import *
from speedtest import Speedtest
root = Tk()

def test():
    download = Speedtest().download()
    upload = Speedtest().upload()
    download_speed = round(download / (10**6),2)
    upload_speed = round(upload / (10**6), 2)

    download_label.config(text = 'Скрорость Загрузки:\n' + str(download_speed)+ 'MbPs')
    upload_label.config(text = 'Скрорость Отдачи:\n' + str(upload_speed)+ 'MbPs')
root.title('SpeedTset')
root.geometry('300x400')

button = Button(root, text = 'нажми на меня',font = 40, command = test )
button.pack(side = BOTTOM,pady = 40)

download_label = Label(root , text = 'Скрорость Загрузки:\n',font = 35)
download_label.pack(pady = (50, 0))

upload_label = Label(root , text = 'Скрорость Отдачи:\n',font = 35)
upload_label.pack(pady = (10,0))

root.mainloop()
