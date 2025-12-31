import tkinter as tk
import random
import winsound

# ------------------ Ventana principal ------------------
ventana = tk.Tk()
ventana.title("Feliz Año Nuevo 🎆")
ventana.minsize(400, 350)
ventana.resizable(True, True)
ventana.config(bg="#0d1b2a")

# ------------------ Título ------------------
titulo = tk.Label(
    ventana,
    text="🎆 Feliz Año Nuevo 🎆",
    font=("Arial", 20, "bold"),
    fg="gold",
    bg="#0d1b2a"
)
titulo.pack(pady=10, fill="x")

# ------------------ Texto nombre ------------------
texto_nombre = tk.Label(
    ventana,
    text="Holi 💖:",
    font=("Arial", 12),
    fg="white",
    bg="#0d1b2a"
)
texto_nombre.pack(pady=5)

entrada_nombre = tk.Entry(
    ventana,
    font=("Arial", 12),
    justify="center"
)
entrada_nombre.insert(0, "Jhuliset")
entrada_nombre.pack(pady=5, ipadx=20)

# ------------------ Mensaje ------------------
mensaje = tk.Label(
    ventana,
    text="",
    font=("Arial", 12),
    fg="white",
    bg="#0d1b2a",
    justify="center"
)
mensaje.pack(pady=10, fill="x")

# ------------------ Área animación ------------------
lienzo = tk.Label(
    ventana,
    text="",
    font=("Arial", 30),
    bg="#0d1b2a"
)
lienzo.pack(pady=15, expand=True)

# ------------------ Datos ------------------
fuegos = ["🎆", "🎇", "✨", "🎉", "🥂", "🕺", "🎈"]
colores = ["#ffbe0b", "#fb5607", "#ff006e", "#8338ec", "#3a86ff"]

# ------------------ Funciones ------------------
def animar(contador=0):
    if contador < 12:
        emoji = random.choice(fuegos)
        color = random.choice(colores)

        lienzo.config(
            text=lienzo.cget("text") + " " + emoji,
            fg=color
        )
        titulo.config(fg=color)
        mensaje.config(fg=color)

        ventana.after(300, animar, contador + 1)
    else:
        lienzo.config(text="🎆🎇 ¡FELIZ AÑO NUEVO! 🎇🎆", fg="gold")
        titulo.config(fg="gold")
        mensaje.config(fg="white")


def detener_musica():
    winsound.PlaySound(None, winsound.SND_PURGE)


def celebrar():
    nombre = entrada_nombre.get().strip()

    if nombre == "":
        mensaje.config(text="✨ Feliz Año Nuevo ✨")
    else:
        mensaje.config(
            text=(
                f"✨ ¡Feliz Año Nuevo, {nombre}! ✨\n"
                "Que este año esté lleno de salud y amor,\n"
                "que te vaya super bien y que todo lo que te propongas se cumpla...\n"
                "Con cariño, Piero 💖"
            )
        )

    # Limpiar animación anterior
    lienzo.config(text="")

    # Reproducir música
    winsound.PlaySound(
    r"C:\Users\HP SUPPORT\OneDrive\Documentos\Dragon City\musica.wav",
    winsound.SND_FILENAME | winsound.SND_ASYNC
)

    
    

    # Detener música después de 9 segundos
    ventana.after(9000, detener_musica)

    # Iniciar animación
    animar()

# ------------------ Botón ------------------
boton = tk.Button(
    ventana,
    text="Celebrar 🎉",
    command=celebrar,
    font=("Arial", 12),
    bg="gold",
    fg="black"
)
boton.pack(pady=10)

# ------------------ Ejecutar ------------------
ventana.mainloop()
