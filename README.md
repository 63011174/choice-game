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
        for F in (StartPage, Page1, Page2, Page3, Page4, Page5, Page6, Page7, Page8): 
   
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
        button1.grid(row = 2, column = 4, padx = 30, pady = 30) 
   
        ## button to show frame 2 with text layout2 
        button2 = ttk.Button(self, text ="Find company that have same job",
        command = lambda : controller.show_frame(Page1)) 
      
        # putting the button in its place by 
        # using grid 
        button2.grid(row = 3, column = 4, padx = 30, pady = 30)


        
   
           
   
   
# second window frame page1  
class Page1(tk.Frame): 
      
    def __init__(self, parent, controller): 
          
        tk.Frame.__init__(self, parent) 
        label = ttk.Label(self, text ="In the next day, Chirs found that the picture No. 25 is went missing. Shawn make a", font = LARGEFONT)
        label1 = ttk.Label(self, text ="comment that ‘Use picture No. 25 for this last time, No matter what’ So he need", font = LARGEFONT)
        label2 = ttk.Label(self, text ="to go ask Shawn, Chris find out that in Shawn picture there is a boat named 'Ekisnake'", font = LARGEFONT)
        label3 = ttk.Label(self, text ="which take place in Greenland. Then He hesitate since Greenland is very far. But he", font = LARGEFONT)
        label4 = ttk.Label(self, text ="see the picture of Shawn, and look like Shawn in the picture is telling him to go.", font = LARGEFONT)
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
        button1.grid(row = 2, column = 4, padx = 30, pady = 30) 
   
        # button to show frame 2 with text 
        # layout2 
        button2 = ttk.Button(self, text ="went by helicopter", 
                            command = lambda : controller.show_frame(Page2)) 
      
        # putting the button in its place by  
        # using grid 
        button2.grid(row = 3, column = 4, padx = 30, pady = 30) 
   
   
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
        button1.grid(row = 2, column = 4, padx = 30, pady = 30) 
   
        # button to show frame 3 with text 
        # layout3 
        button2 = ttk.Button(self, text ="Went down with a sliding board", 
                            command = lambda : controller.show_frame(Page3)) 
      
        # putting the button in its place by 
        # using grid 
        button2.grid(row = 3, column = 4, padx = 30, pady = 30) 


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
        button1 = ttk.Button(self, text ="Chris ask his mother what he going to do about Shawn Clues.", 
                            command = lambda : controller.show_frame(Page4)) 
      
        # putting the button in its place by  
        # using grid 
        button1.grid(row = 2, column = 4, padx = 30, pady = 30) 
   
        # button to show frame 3 with text 
        # layout3 
        button2 = ttk.Button(self, text ="Chris decide to clear brain, and talking to his mother", 
                            command = lambda : controller.show_frame(Page4)) 
      
        # putting the button in its place by 
        # using grid 
        button2.grid(row = 3, column = 4, padx = 30, pady = 30)


# third window frame page4
class Page4(tk.Frame):  
    def __init__(self, parent, controller): 
        tk.Frame.__init__(self, parent) 
        label = ttk.Label(self, text ="Chris mother say that “Shawn? Guy who comes to ask for your work schedule?”", font = LARGEFONT)
        label1 = ttk.Label(self, text ="Chris ask his mother that “Why didn’t you tell me?” Mother say that she already", font = LARGEFONT)
        label2 = ttk.Label(self, text ="told Chris but he didn't hear. And mother told Chris that Shawn say this ", font = LARGEFONT)
        label3 = ttk.Label(self, text ="'I want a cake so I can continues to Warlord.' Chris go search up that Warlord", font = LARGEFONT)
        label4 = ttk.Label(self, text ="is the Himalaya Mountain in Afghanistan. Chris flys there with no hesitation,", font = LARGEFONT)
        label5 = ttk.Label(self, text ="he decide to hire a guide. Since he don't know the ways and how to survive as well.", font = LARGEFONT)
        label6 = ttk.Label(self, text ="Guide offer him a nut or a leaf that eat for decrease hungry. So you choose...", font = LARGEFONT)
        
        label.grid(row = 0, column = 1, padx = 10, pady = 10)
        label1.grid(row = 1, column = 1, padx = 10, pady = 10)
        label2.grid(row = 2, column = 1, padx = 10, pady = 10)
        label3.grid(row = 3, column = 1, padx = 10, pady = 10)
        label4.grid(row = 4, column = 1, padx = 10, pady = 10)
        label5.grid(row = 5, column = 1, padx = 10, pady = 10)
        label6.grid(row = 6, column = 1, padx = 10, pady = 10)
   
        # button to show frame 2 with text 
        # layout2 
        button1 = ttk.Button(self, text ="Nut from squirrel nest", 
                            command = lambda : controller.show_frame(Page5)) 
      
        # putting the button in its place by  
        # using grid 
        button1.grid(row = 2, column = 4, padx = 30, pady = 30) 
   
        # button to show frame 3 with text 
        # layout3 
        button2 = ttk.Button(self, text ="Tree leaf that find easier", 
                            command = lambda : controller.show_frame(Page5)) 
      
        # putting the button in its place by 
        # using grid 
        button2.grid(row = 3, column = 4, padx = 30, pady = 30)


# third window frame page5
class Page5(tk.Frame):  
    def __init__(self, parent, controller): 
        tk.Frame.__init__(self, parent) 
        label = ttk.Label(self, text ="if you choose the nut the guide luckily found a squirrel nest and it taste better", font = LARGEFONT)
        label1 = ttk.Label(self, text ="for sure. After they get to the spot the guide say ‘we can only guide you here,", font = LARGEFONT)
        label2 = ttk.Label(self, text ="you have to go on alone.’ Chris went through a lot of cold weather and low", font = LARGEFONT)
        label3 = ttk.Label(self, text ="oxygen. Until there a phone call from his mother that ask where is he now.", font = LARGEFONT)
        label4 = ttk.Label(self, text ="Suddenly, there are a voice from beside Chris. “Hey, friend. Could you keep it", font = LARGEFONT)
        label5 = ttk.Label(self, text ="low? I am trying to take picture of a snow tiger”, Shawn was speaking in the cover.", font = LARGEFONT)
        label6 = ttk.Label(self, text ="It take very long to finally catch up with Shawn. Chris almost cry. So Chris decide to..", font = LARGEFONT)
        
        label.grid(row = 0, column = 1, padx = 10, pady = 10)
        label1.grid(row = 1, column = 1, padx = 10, pady = 10)
        label2.grid(row = 2, column = 1, padx = 10, pady = 10)
        label3.grid(row = 3, column = 1, padx = 10, pady = 10)
        label4.grid(row = 4, column = 1, padx = 10, pady = 10)
        label5.grid(row = 5, column = 1, padx = 10, pady = 10)
        label6.grid(row = 6, column = 1, padx = 10, pady = 10)
   
        # button to show frame 2 with text 
        # layout2 
        button1 = ttk.Button(self, text ="Tell Shawn who you are", 
                            command = lambda : controller.show_frame(Page6)) 
      
        # putting the button in its place by  
        # using grid 
        button1.grid(row = 2, column = 4, padx = 30, pady = 30) 
   
        # button to show frame 3 with text 
        # layout3 
        button2 = ttk.Button(self, text ="Ask about the picture No.25", 
                            command = lambda : controller.show_frame(Page6)) 
      
        # putting the button in its place by 
        # using grid 
        button2.grid(row = 3, column = 4, padx = 30, pady = 30)


# third window frame page6
class Page6(tk.Frame):  
    def __init__(self, parent, controller): 
        tk.Frame.__init__(self, parent) 
        label = ttk.Label(self, text ="Shawn was shock for second because he didn’t think Chris would come all the ways", font = LARGEFONT)
        label1 = ttk.Label(self, text ="here to just ask a question. Shawn answer that 'The picture No. 25 is in your", font = LARGEFONT)
        label2 = ttk.Label(self, text ="I thought it would be funny to do that.' But Chris said he already put his ", font = LARGEFONT)
        label3 = ttk.Label(self, text ="wallet in the bin at his mother’s house. Shawn said that picture is a true beauty.", font = LARGEFONT)
        label4 = ttk.Label(self, text ="Then what Shawn waiting to take picture is coming out. Snow tiger that not", font = LARGEFONT)
        label5 = ttk.Label(self, text ="usually coming out it is animal that is rarely hard to saw these days.", font = LARGEFONT)
        label6 = ttk.Label(self, text ="Now, you are Shawn this time and you making decision taking the photo or not", font = LARGEFONT)
        
        label.grid(row = 0, column = 1, padx = 10, pady = 10)
        label1.grid(row = 1, column = 1, padx = 10, pady = 10)
        label2.grid(row = 2, column = 1, padx = 10, pady = 10)
        label3.grid(row = 3, column = 1, padx = 10, pady = 10)
        label4.grid(row = 4, column = 1, padx = 10, pady = 10)
        label5.grid(row = 5, column = 1, padx = 10, pady = 10)
        label6.grid(row = 6, column = 1, padx = 10, pady = 10)
   
        # button to show frame 2 with text 
        # layout2 
        button1 = ttk.Button(self, text ="Take picture ", 
                            command = lambda : controller.show_frame(Page7)) 
      
        # putting the button in its place by  
        # using grid 
        button1.grid(row = 2, column = 4, padx = 30, pady = 30) 
   
        # button to show frame 3 with text 
        # layout3 
        button2 = ttk.Button(self, text ="Don’t take", 
                            command = lambda : controller.show_frame(Page7)) 
      
        # putting the button in its place by 
        # using grid 
        button2.grid(row = 3, column = 4, padx = 30, pady = 30)



# third window frame page7
class Page7(tk.Frame):  
    def __init__(self, parent, controller): 
        tk.Frame.__init__(self, parent) 
        label = ttk.Label(self, text ="Shawn saw Snow tiger and wait but not take a picture. Shawn said ", font = LARGEFONT)
        label1 = ttk.Label(self, text ="“There were Times when these Beautiful Moment Happen, I want to Kept it Here”. ", font = LARGEFONT)
        label2 = ttk.Label(self, text ="when Chris go back to New York. His mom come pick him up at airport and give ", font = LARGEFONT)
        label3 = ttk.Label(self, text ="him money and his 'WALLET'. She said that she always keep her son things. ", font = LARGEFONT)
        label4 = ttk.Label(self, text ="In the end, Chirs go to the office and toss the picture to the manager and say", font = LARGEFONT)
        label5 = ttk.Label(self, text ="“Here, your picture number 25. Every people in company work hard for these magazine” ", font = LARGEFONT)
        label6 = ttk.Label(self, text ="Chris get out with the smile om him. Next day, Chris write resume about his life", font = LARGEFONT)
        label7 = ttk.Label(self, text ="what have he been through. This is your final Choice, the decision you are ", font = LARGEFONT)
        label8 = ttk.Label(self, text ="on is number 9 making your move now before you fall back to number 8.", font = LARGEFONT)
        
        label.grid(row = 0, column = 1, padx = 10, pady = 5)
        label1.grid(row = 1, column = 1, padx = 10, pady = 5)
        label2.grid(row = 2, column = 1, padx = 10, pady = 5)
        label3.grid(row = 3, column = 1, padx = 10, pady = 5)
        label4.grid(row = 4, column = 1, padx = 10, pady = 5)
        label5.grid(row = 5, column = 1, padx = 10, pady = 5)
        label6.grid(row = 6, column = 1, padx = 10, pady = 5)
        label7.grid(row = 7, column = 1, padx = 10, pady = 5)
        label8.grid(row = 8, column = 1, padx = 10, pady = 5)
   
        # button to show frame 2 with text 
        # layout2 
        button1 = ttk.Button(self, text ="Order coffee at the cafe", 
                            command = lambda : controller.show_frame(Page8)) 
      
        # putting the button in its place by  
        # using grid 
        button1.grid(row = 2, column = 4, padx = 30, pady = 35) 
   
        # button to show frame 3 with text 
        # layout3 
        button2 = ttk.Button(self, text ="Buy a newspaper to read", 
                            command = lambda : controller.show_frame(Page8)) 
      
        # putting the button in its place by 
        # using grid 
        button2.grid(row = 3, column = 4, padx = 30, pady = 35)


# third window frame page8
class Page8(tk.Frame):  
    def __init__(self, parent, controller): 
        tk.Frame.__init__(self, parent) 
        label = ttk.Label(self, text ="When you get up and walk to get what on your thought, but there are small shop ", font = LARGEFONT)
        label1 = ttk.Label(self, text ="selling magazine on the way. You take a good look at it and see the title ", font = LARGEFONT)
        label2 = ttk.Label(self, text ="named “FINAL ISSUE: Dedicated to the People Who Made It” ", font = LARGEFONT)
        label3 = ttk.Label(self, text ="And the picture Number 25 is being use on their. It is the picture of", font = LARGEFONT)
        label4 = ttk.Label(self, text ="Chris himself that working on these magazine, for a long time. ", font = LARGEFONT)
        label5 = ttk.Label(self, text ="Shawn want to tell people that every people have their role in them. ", font = LARGEFONT)
        label6 = ttk.Label(self, text ="Now, that you have read till the end. What is your life now, happy or not", font = LARGEFONT)
        
        label.grid(row = 0, column = 1, padx = 10, pady = 10)
        label1.grid(row = 1, column = 1, padx = 10, pady = 10)
        label2.grid(row = 2, column = 1, padx = 10, pady = 10)
        label3.grid(row = 3, column = 1, padx = 10, pady = 10)
        label4.grid(row = 4, column = 1, padx = 10, pady = 10)
        label5.grid(row = 5, column = 1, padx = 10, pady = 10)
        label6.grid(row = 6, column = 1, padx = 10, pady = 10)

        



   
# Driver Code 
app = tkinterApp() 
app.mainloop()



