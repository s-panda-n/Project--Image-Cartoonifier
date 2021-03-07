# Project--Image-Cartoonifier
An OpenCV project using various libraries in Python that Modifies and creates a new Cartoonified Image from given input Image and saves it to the provided address.


# Step 1: Importing the required modules
We will import the following modules:

CV2: Imported to use OpenCV for image processing
easygui: Imported to open a file box. It allows us to select any file from our system.
Numpy: Images are stored and processed as numbers. These are taken as arrays. We use NumPy to deal with arrays.
Imageio: Used to read the file which is chosen by file box using a path.
Matplotlib: This library is used for visualization and plotting. Thus, it is imported to form the plot of images.
OS: For OS interaction. Here, to read the path and save images to that path.

# Step 2: Building a File Box to choose a particular file
In this step, we will build the main window of our application, where the buttons, labels, and images will reside. We also give it a title by title() function.
The code in Step 2 opens the file box, i.e the pop-up box to choose the file from the device, which opens every time you run the code. fileopenbox() is the method in easyGUI module which returns the path of the chosen file as a string.

# Step 3: Writing the main function
Imread is a method in cv2 which is used to store images in the form of numbers. This helps us to perform operations according to our needs. The image is read as a numpy array, in which cell values depict R, G, and B values of a pixel.
To convert an image to a cartoon, multiple transformations are done. Firstly, an image is converted to a Grayscale image. Then, the Grayscale image is smoothened, and we try to extract the edges in the image. Finally, we form a color image and mask it with edges. This creates a beautiful cartoon image with edges and lightened color of the original image.
After each transformation, we resize the resultant image using the resize() method in cv2 and display it using imshow() method. This is done to get more clear insights into every single transformation step.
To smoothen an image, we simply apply a blur effect. This is done using medianBlur() function. Here, the center pixel is assigned a mean value of all the pixels which fall under the kernel. In turn, creating a blur effect.
We prepare a lightened color image that we mask with edges at the end to produce a cartoon image. We use bilateralFilter which removes the noise. It can be taken as smoothening of an image to an extent.
Cartoon effect has two specialties:
  1.Highlighted Edges
  2.Smooth colors
We combine the two specialties. This is done using MASKING. We perform bitwise and on two images to mask them. 

# Step 4: A new function is defined to save the final Image
imwrite() method of cv2 is used to save the file at the path mentioned. cv2.cvtColor(CartoonizedImage, cv2.COLOR_RGB2BGR) is used to assure that no color get extracted or highlighted while we save our image. Thus, at last, the user is given confirmation that the image is saved with the name and path of the file.

# Step 5: Main function to build the tkinter window
A display window pops up showing buttons as soon as the image transformation is done. It gives an option to the user to select and save cartoonified image. After the image is Saved, it also produces an option to Close the window.
