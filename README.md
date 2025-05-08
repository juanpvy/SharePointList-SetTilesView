# SharePoint List view from "List" to "Tiles" 
Change the list view layout to "Gallery Layout"

# Description 
In SharePoint Online we can create a "List View" and display its information applying a set of differents functionalities.

One of them is display the information in: 
* "List": Flat view , similar to excel.
* "Gallery" : Squares or cards.

What if a need change the view from "List" to "Gallery", SharePoint does not have section/button to perform this update OOTB. 
One alternative is create a new view and select the "Gallery Layout".

![image](https://github.com/user-attachments/assets/2070b243-c66a-48ba-96df-3870a39217ba)

That is OK, but in my case I have several lists and views configurated in severals "Modern Pages" , with this approach I should update each page (as you can imagine, is a lot of work that I am trying to avoid).

# Solution

As a have mentioned, a have a lot of lists and pages using these list view , create and recreate views is not feasible but SharePoint has a REST API and change the view layout is possible with the following code.

`sp.web.lists.getByTitle("<LIST_NAME>").views.getByTitle("<LIST_TITLE>").update({ViewType2:"TILES"})`

I am using the Google Chrome Extension "SP Editor" in order to execute the code. This extensions use pnp-js library as a wrapped of SharePoint REST API.

https://chromewebstore.google.com/detail/sp-editor/ecblfcmjnbbgaojblcpmjoamegpbodhd?hl=ES&pli=1

![image](https://github.com/user-attachments/assets/c98ac0b5-1838-40a5-92fc-c0f0aff9482a)


Basically after install "SP Editor" open "Developer Tools (F12)" then "SharePoint" Tab and  click in "PnP JS Console"
![image](https://github.com/user-attachments/assets/e2cde1a9-45eb-420d-b7e8-3f96333b895e)

Run the code (CTRL + D) and that it's, the layouts is updated and don't worry where the view is used.
![FlatToGallery](https://github.com/user-attachments/assets/c7abbf63-190e-4a6d-8d38-f6a15d3cb8c8)
