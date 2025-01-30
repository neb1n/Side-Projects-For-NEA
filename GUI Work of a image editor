from tkinter import *
from tkinter import ttk
from PIL import *

root = Tk()
root.title("Image Editor")

image = PhotoImage(file=" ")

#! Frames
tools_frame = Frame(root, width=200, height=400, bg="skyblue")
tools_frame.pack(padx=5, pady=5, side=LEFT, fill=Y)

Label(
    tools_frame,
    text="Original Image",
    bg="skyblue",
).pack(padx=5, pady=5)
thumbnail_image = image.subsample(5, 5)
Label(tools_frame, image=thumbnail_image).pack(padx=5, pady=5)

#! Tabs
notebook = ttk.Notebook(tools_frame)
notebook.pack(expand=True, fill="both")

tools_tab = Frame(notebook, bg="lightblue")
tools_var = StringVar(value="None")
for tool in ["Resizing", "Rotating"]:
    Radiobutton(
        tools_tab,
        text=tool,
        variable=tools_var,
        value=tool,
        bg="lightblue",
    ).pack(anchor="w", padx=20, pady=5)
    Scale(
        tools_tab,
        from_= 0,
        to = 100,
        orient = HORIZONTAL
        ).pack(anchor= "w", padx = 20, pady = 5)


filters_tab = Frame(notebook, bg="lightgreen")
filters_var = StringVar(value="None")

for filter in ["Blurring", "Sharpening"]:
    Radiobutton(
        filters_tab,
        text=filter,
        variable=filters_var,
        value=filter,
        bg="lightgreen",
    ).pack(anchor="w", padx=20, pady=5)
    Scale(
        filters_tab,
        from_=0,
        to = 100,
        orient = HORIZONTAL
    ).pack(anchor = "w", padx = 20, pady = 5)

notebook.add(tools_tab, text="Tools")
notebook.add(filters_tab, text="Filters")

# Image frame
image_frame = Frame(root, width=400, height=400, bg="grey")
image_frame.pack(padx=5, pady=5, side=RIGHT)
display_image = image.subsample(2, 2)
Label(
    image_frame,
    text="Edited Image",
    bg="grey",
    fg="white",
).pack(padx=5, pady=5)
Label(image_frame, image=display_image).pack(padx=5, pady=5)

root.mainloop()
