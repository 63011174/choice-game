# choice-game
# this game is made for a python project

import tkinter as tk 
from tkinter import ttk 
   
  
LARGEFONT =("Verdana", 15) 
   
class tkinterApp(tk.Tk): 
      
    # __init__ function for class tkinterApp  
    def __init__(self, *args, **kwargs):  
          
        # __init__ function for class Tk 
        tk.Tk.__init__(self, *args, **kwargs) 
          
        # creating a container 
        container = tk.Frame(self)   
        container.pack(side = "top", fill = "both", expand = True)  
   
        container.grid_rowconfigure(0, weight = 1) 
        container.grid_columnconfigure(0, weight = 1) 
   
        # initializing frames to an empty array 
        self.frames = {}   
   
        # iterating through a tuple consisting 
        # of the different page layouts 
        for F in (StartPage, Page1, Page2, Page3): 
   
            frame = F(container, self) 
   
            # initializing frame of that object from 
            # startpage, page1, page2 respectively with  
            # for loop 
            self.frames[F] = frame  
   
            frame.grid(row = 0, column = 0, sticky ="nsew") 
   
        self.show_frame(StartPage) 
   
    # to display the current frame passed as 
    # parameter 
    def show_frame(self, cont): 
        frame = self.frames[cont] 
        frame.tkraise() 
   
# first window frame startpage 
   
class StartPage(tk.Frame): 
    def __init__(self, parent, controller):  
        tk.Frame.__init__(self, parent) 
          
        # label of frame Layout 2 
        
        label1 = ttk.Label(self, text='In the morning, Chris wake up and prepare himself to go to work.', font = LARGEFONT)
        label2 = ttk.Label(self, text="Chris job’s is to printing and posting the picture which was taken by", font = LARGEFONT)
        label3 = ttk.Label(self, text="headquarter of the company named ‘Shawn’. Today, Chris being told,", font = LARGEFONT)
        label4= ttk.Label(self, text="he is going to be fire by next week, since Chris’s job is being replace by robot.", font = LARGEFONT)
        label5 = ttk.Label(self, text="Chris go back home and start wondering he was living alone for many", font = LARGEFONT)
        label6 = ttk.Label(self, text="years, and there is nothing new and excited during his daily life.", font = LARGEFONT)
        label = ttk.Label(self, text ="\nNow it times for your first decision", font = LARGEFONT)
        # putting the grid in its place by using 
        # grid 
        label.grid(row = 6, column = 1, padx = 10, pady = 10)  
        label1.grid(row = 0, column = 1, padx = 10, pady = 10)
        label2.grid(row = 1, column = 1, padx = 10, pady = 10)
        label3.grid(row = 2, column = 1, padx = 10, pady = 10)
        label4.grid(row = 3, column = 1, padx = 10, pady = 10)
        label5.grid(row = 4, column = 1, padx = 10, pady = 10)
        label6.grid(row = 5, column = 1, padx = 10, pady = 10)

        
        button1 = ttk.Button(self, text ="Look for the new job", 
        command = lambda : controller.show_frame(Page1)) 
      
        # putting the button in its place by 
        # using grid 
        button1.grid(row = 1, column = 4, padx = 10, pady = 10) 
   
        ## button to show frame 2 with text layout2 
        button2 = ttk.Button(self, text ="Find company that have same job", 
        command = lambda : controller.show_frame(Page1)) 
      
        # putting the button in its place by 
        # using grid 
        button2.grid(row = 2, column = 4, padx = 10, pady = 10) 
   
           
   
   
# second window frame page1  
class Page1(tk.Frame): 
      
    def __init__(self, parent, controller): 
          
        tk.Frame.__init__(self, parent) 
        label = ttk.Label(self, text ="In the next day, Chirs found that the picture No. 25 is went missing", font = LARGEFONT)
        label1 = ttk.Label(self, text ="Shawn make a comment that ‘Use picture No. 25 for this last time, ", font = LARGEFONT)
        label2 = ttk.Label(self, text ="No matter what’. So he need to go ask Shawn, Chris find out that in", font = LARGEFONT)
        label3 = ttk.Label(self, text ="Shawn picture there is a boat named “Ekisnake”, which take place in Greenland.", font = LARGEFONT)
        label4 = ttk.Label(self, text ="Then He hesitate since Greenland is very far. But he make decision with no hesitate.", font = LARGEFONT)
        label5 = ttk.Label(self, text ="Chirs go to the airport and take flight to Greenland. Chris alive and ask people,", font = LARGEFONT)
        label6 = ttk.Label(self, text ="“Do you know where Shawn went?” The bartender say he went to the boat named “Ekisnake”.", font = LARGEFONT)
        label6 = ttk.Label(self, text ="by this time the rain start falling and sea start to unclaims. What's your choice...", font = LARGEFONT)
        
        label.grid(row = 0, column = 1, padx = 10, pady = 10)
        label1.grid(row = 1, column = 1, padx = 10, pady = 10)
        label2.grid(row = 2, column = 1, padx = 10, pady = 10)
        label3.grid(row = 3, column = 1, padx = 10, pady = 10)
        label4.grid(row = 4, column = 1, padx = 10, pady = 10)
        label5.grid(row = 5, column = 1, padx = 10, pady = 10)
        label6.grid(row = 6, column = 1, padx = 10, pady = 10)
   
        # button to show frame 2 with text 
        # layout2 
        button1 = ttk.Button(self, text ="Went to the boat by another boat ", 
                            command = lambda : controller.show_frame(Page2)) 
      
        # putting the button in its place  
        # by using grid 
        button1.grid(row = 1, column = 4, padx = 10, pady = 10) 
   
        # button to show frame 2 with text 
        # layout2 
        button2 = ttk.Button(self, text ="went by helicopter", 
                            command = lambda : controller.show_frame(Page2)) 
      
        # putting the button in its place by  
        # using grid 
        button2.grid(row = 2, column = 4, padx = 10, pady = 10) 
   
   
   #label = ttk.Label(self, text ="", font = LARGEFONT)
   
# third window frame page2 
class Page2(tk.Frame):  
    def __init__(self, parent, controller): 
        tk.Frame.__init__(self, parent) 
        label = ttk.Label(self, text ="you are on helicopter and captain told you to jump down to the boat", font = LARGEFONT)
        label1 = ttk.Label(self, text ="But Chris jump wrong side, and he met shark but he manage to escape saftly", font = LARGEFONT)
        label2 = ttk.Label(self, text ="By the time he alive at the boat, the captain said Shawn already go ", font = LARGEFONT)
        label3 = ttk.Label(self, text ="Next morning the boat arrive at Iceland. He go to the hotel and ask the owner", font = LARGEFONT)
        label4 = ttk.Label(self, text ="who look like packing thing in a hurry answer that “he went down the hill to airport.", font = LARGEFONT)
        label5 = ttk.Label(self, text ="I was just sending him there 15 min ago.” Chris went to see the ways down the hill.", font = LARGEFONT)
        label6 = ttk.Label(self, text ="The ways down is pretty steep, Now you have to decide for Chris next move... ", font = LARGEFONT)
        
        label.grid(row = 0, column = 1, padx = 10, pady = 10)
        label1.grid(row = 1, column = 1, padx = 10, pady = 10)
        label2.grid(row = 2, column = 1, padx = 10, pady = 10)
        label3.grid(row = 3, column = 1, padx = 10, pady = 10)
        label4.grid(row = 4, column = 1, padx = 10, pady = 10)
        label5.grid(row = 5, column = 1, padx = 10, pady = 10)
        label6.grid(row = 6, column = 1, padx = 10, pady = 10)
   
        # button to show frame 2 with text 
        # layout2 
        button1 = ttk.Button(self, text ="Went down with a skate board", 
                            command = lambda : controller.show_frame(Page3)) 
      
        # putting the button in its place by  
        # using grid 
        button1.grid(row = 1, column = 4, padx = 10, pady = 10) 
   
        # button to show frame 3 with text 
        # layout3 
        button2 = ttk.Button(self, text ="Went down with a sliding board", 
                            command = lambda : controller.show_frame(Page3)) 
      
        # putting the button in its place by 
        # using grid 
        button2.grid(row = 2, column = 4, padx = 10, pady = 10) 


# third window frame page3 
class Page3(tk.Frame):  
    def __init__(self, parent, controller): 
        tk.Frame.__init__(self, parent) 
        label = ttk.Label(self, text ="Chris arrive safely and look for Shawn, but there no one there in the airport then", font = LARGEFONT)
        label1 = ttk.Label(self, text ="there is warning sound of “Volcanic eruption”. Luckily the hotel owner went down", font = LARGEFONT)
        label2 = ttk.Label(self, text ="after Chris and pick him up by the car and they both got out safely. And this was", font = LARGEFONT)
        label3 = ttk.Label(self, text ="the first time Chris saw Shawn, he was standing above the air plane and taking picture ", font = LARGEFONT)
        label4 = ttk.Label(self, text ="of volcano eruption. After that Chris was left alone with nothing lead to Shawn ", font = LARGEFONT)
        label5 = ttk.Label(self, text ="and no money left to go on. He decide to go back to New York and Chris go to mother", font = LARGEFONT)
        label6 = ttk.Label(self, text ="apartment. At that time Chris has no money left so he put his wallet in the bin. Then...", font = LARGEFONT)
        
        label.grid(row = 0, column = 1, padx = 10, pady = 10)
        label1.grid(row = 1, column = 1, padx = 10, pady = 10)
        label2.grid(row = 2, column = 1, padx = 10, pady = 10)
        label3.grid(row = 3, column = 1, padx = 10, pady = 10)
        label4.grid(row = 4, column = 1, padx = 10, pady = 10)
        label5.grid(row = 5, column = 1, padx = 10, pady = 10)
        label6.grid(row = 6, column = 1, padx = 10, pady = 10)
   
        # button to show frame 2 with text 
        # layout2 
        button1 = ttk.Button(self, text ="Chris ask your mother what you going to do next about Shawn Clues.", 
                            command = lambda : controller.show_frame(Page2)) 
      
        # putting the button in its place by  
        # using grid 
        button1.grid(row = 1, column = 4, padx = 10, pady = 10) 
   
        # button to show frame 3 with text 
        # layout3 
        button2 = ttk.Button(self, text ="Chris decide to put you weight out and clear brain. ", 
                            command = lambda : controller.show_frame(Page2)) 
      
        # putting the button in its place by 
        # using grid 
        button2.grid(row = 2, column = 4, padx = 10, pady = 10)





   
# Driver Code 
app = tkinterApp() 
app.mainloop()
