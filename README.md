from tkinter import *
from tkinter import ttk

class Siswa:
    def __init__(self):
        self.nama = ""
        self.status = ""
        
    def set_nama(self, nama):
        self.nama = nama
    def get_nama(self):
        return self.nama

    def set_status(self, status):
        self.status = status
    def get_status(self):
        return self.status

def tambah_data():
    nama = nama_entry.get()
    status = status_entry.get()
    
    siswa = Siswa()
    
    siswa.set_nama(nama)
    siswa.set_status(status)
    
    data_nama.config(text=siswa.get_nama())
    data_status.config(text=siswa.get_status())

root = Tk()
root.title('Form Data Siswa')
root.geometry('500x500')

judul = Label(root, text='Data Diri Siswa', font=('Arial', 14, 'bold'), pady=10)
judul.pack()

frame_data = Frame(root)
frame_data.pack()

nama_label = Label(frame_data, text='Nama')
nama_entry = Entry(frame_data, width=30)
nama_label.grid(row=0, column=0, pady=5, padx=5)
nama_entry.grid(row=0, column=1, pady=5, padx=5)

status_label = Label(frame_data, text='Status')
status_entry = Entry(frame_data, width=30)
status_label.grid(row=1, column=0, pady=5, padx=5)
status_entry.grid(row=1, column=1, pady=5, padx=5)

tombol_tambah = Button(frame_data, text='Tambah Data', command=tambah_data)
tombol_tambah.grid(row=2, column=1)

# Frame hasil data
frame_hasil = Frame(root)
frame_hasil.pack()

label_nama = Label(frame_hasil, 
                   text='Nama :')
label_nama.grid(row=0, column=0)

data_nama = Label(frame_hasil, 
                  text="")
data_nama.grid(row=0, column=1)

label_status = Label(frame_hasil, 
                     text='Status :')
label_status.grid(row=1, column=0)

data_status = Label(frame_hasil, 
                    text="")
data_status.grid(row=1, column=1)

root.mainloop()