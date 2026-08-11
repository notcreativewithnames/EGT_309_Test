# EGT309_26S1_test


### Name: see long hua brian
### Admin Number: 234592R
### Github Link: https://github.com/notcreativewithnames/EGT_309_Test

#### Q2(a): Documenting Your Python Class:
line 2 - defines and initalizes class ModularPipelineLayoutLM with variables self, model_id: str = "impira/layoutlm-document-qa"
line 3 - uses pipeline called self.qa_pipeline to run a model with task document question answering along with its model=model_id
line 4 runs a function called load_document using variables self, document_source:str
    is_url variable checks for links starting with http:// or https://
line 8 - if function checks for links ending with .pdf and if is_url is http:// or https:// and ends with .pdf,
    then call new variable response to get document source and its status
    define new variable called pages to convert from pdf bytes and get document content
        else convert pdf from file path for pages variable to get document source directly
    get updated variable pages[0] back at end of function
Line 14 - else:
        if is_url = https:// or http://, then get response variable with source and status and get back an image run through BytesIO converted to RGB
Line 19 - else:
           get back an image directly from document source converted to RGB
Line 21 - defines a function called "ask" with variables self, image: Image.Image, question: str)
    writes result variable using pipeline to get image and question
Line 23 - if isinstance checks for result and if its a list, along with the result have a length of greater than 0:
    write res variable = result[0]
Line 25 - elif isinstance checks for result and if its a dict, call res = result
Line 27 - else: if not dict or list, print "No valid answer found"
Line 29 - write new variable answer = use res.get to get answer
score variable = use res.get to get score - note: res.get is from the called in pipeline model
Line 32 - if function checks for answer then returns an answer with confidence score
if no answer then print "No Valid answer found"


#### Q2(d) Suggest Improvements to the Code:
More documentation, current code has no comments or anything else to help people exploring this code understand at a first glance
Robustness, current code has no error handling for example, if_url could easily be corrupted and cause the function to freeze as it attempts to open a corrupted image.
additionally, you can put nonsense as the url and it will run and fail sliently.


#### Q4 Advanced Github features implemented: