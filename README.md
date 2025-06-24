# StudyOCRwithTesseract

<div>
  🤓 I am sharing an study algorithm of some basic techniques for extracting text from images using OCR techniques with Python and Tesseract. 🤓
</div>

</b>
</b>

## So, what is OCR?

<div>
 🟣 Acronym meaning Optical Character Recognition. It is a technology that converts images of text into a format readable by computers. OCR allows for the reading of printed or handwritten documents, extracting the transcription of the text contained in them. It is a widely used tool for digitizing documents, editing, and processing the extracted textual content.
</div>

</b>
</b>

## Tesseract

<div>
  </b>
  🟣Tesseract started as an OCR engine, allowing for some text extraction operations from images. It evolved and became a widely used open-source algorithm, capable of recognizing text in over 100 languages.
  
  </b>
  </b>
  
  
  🟣This tool combines deep learning (with complex, multi-layer algorithms capable of learning patterns in large databases) and computer vision, which applies mathematical resources (especially geometry and algebra) to analyze images and identify elements. This powerful combination allows Tesseract to be a great tool for identifying texts with high precision, the ability to handle variations in formatting and writing style, identification of structured elements in documents, and automation of tasks. 
  
  </b>
  
  🟣The Tesseract also uses Natural Language Processing techniques. This allows the algorithm to understand the context, enabling more precise and complex analyses, as well as the classification of documents according to their content (keywords).
  
  </b>
  
  🟣For the machine, an image is interpreted as a matrix, composed of basic elements called pixels. In the RGB format, the image is made up of 3 layers (red, blue, and green). Each layer corresponds to the value of these base colors, and their concatenation forms the pixel that we can visualize with the naked eye. Each pixel is in the range of integers from 0 to 255.Thus, any operation on the image corresponds to a linear transformation applied to these pixels. The techniques used by Tesseract perform convolution operations on the image, extract the main features, edges, and from that, apply deep learning processes to identify the object it was trained for. In this case, it is capable of learning corresponding characters of a language, combined with natural language processing techniques where, in addition to identifying the object, it can, with proper training, extract keywords and perform other processes on the extracted text (now treating it as a string or collection of strings).
  
  </b>
  
  🟣Object detection techniques in images also follow similar principles, but this will be addressed in another repository.
  
</div>

</b>
</b>

## Processing the image and using Tesseract

<div>

  🟣 We can use a range of libraries to call and process images. However, in this content, we will discuss OpenCV and also PIL. OpenCV reads the image in BGR format, while PIL reads the image directly in RGB, but we need to use Matplotlib to display the image.

  </b>
   
  🟣 After opening the directory and the image, it is necessary to use OpenCV to transform the image from BGR (initially, the image is read in this format) to RGB. This way, we can correctly visualize the colors of the image. It is possible to operate Tesseract on an RGB image, but it is good practice to convert the image to grayscale. Personally, I always test extraction on the grayscale image or using other filters. This allows me to make a careful selection of what will yield the best results. In the literature, Tesseract recommends a white background in the image and black letters (corresponding to a binary environment, where the matrix formed by the now single-channel layer will be made of 0 and 255). Let's delve into the various techniques in other topics.
  
  </b>
  
  🟣Using pytesseract.image_to_OSD("image_path"), you can print informations from the image, like page number, orientation and language.
  
  </b>
  
  🟣 Another very important resource of Tesseract is the selection of text and the creation of bounding boxes for each letter or word. It is also possible to visualize the extracted word on top of each drawn box. Tesseract, being a resource that uses neural networks, extracts characters and words with a certain level of confidence. To draw the bounding boxes, we only work with words that have a high degree of confidence.
  
  </b>
  
  🟣When we use pytesseract.image_to_data() with the image and language parameters, in addition to out_put_type= Output.DICT, it will print in a dictionary the attributes that I explained within the code itself. Some of these values represent predictions and also the location of the found words. Therefore, these specific values are used as coordinates to draw the rectangle around the word and also the identified word.
</div>





