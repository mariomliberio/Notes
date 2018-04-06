# Spacemacs

## Getting Started

**Buffers, Windows & Frames**

- What we usually call windows (in a browser or file manager** are called frames in emacs, pretty self explanatory and interchangable terms. 
- In emacs, windows are comparable to tabs in a browser, for example when taking notes from the spacemacs begginers tutorial I have two windows in one frame, on the left the tutorial itself and on the right the markdown file where im taking notes. We can open the window menu in Spacemacs by pressing SPC w.
- Buffers are your currently opened documents, there are many ways of organizing buffers in your frame. For example you could have two buffers each on one window, like i just described in the window example. However you could also have one window open in which you cycle through different buffers by pressing SPC TAB to switch between your 2 last used or SPC b to have more options for multiple buffers.

**Accesing files**

- Files are easilly accesible by pressing SPC f. You can navigate to a file using SPC f f and pressing enter to open it. Acessing recently opened files can be done pressing SPC f r.

## Configuring Spacemacs

**Adding Language support and other features: Using Layers**

- Spacemacs divides its configuration into self contained units called config layers. They are stacked on top of each other to create a custom configuration.
- Spacemacs uses a dotfile called ~/.spacemacs to control which layers to load.  
