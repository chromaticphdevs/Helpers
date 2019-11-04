# Helpers
PHP BUILT IN HELPERS

#HOW TO USE FILE Helper

//initiate the file helper
$file = new File();

$file->setFile($_FILES['uploadFileName'])
->setDIR(YOUR_UPLOAD_PATH)
->setPrefix('testUpload') //optional
->upload();

//to check if there is an error do 

if(!empty($file->getErrors())) {
 //errors are already imploded so you can use it as string
 echo $file->getErrors();
 die();
}else{
  //get the uploaded File name
  echo $file->getFileUploadName();
}

//You can add more extension by calling the method
$file->addFileType('docx') or $file->addFileType(['docx' , 'doc' , 'xlsx'])
//You can also specify the your desired return name of uploaded file by calling

$file->setCustomName('uploadName')

change the max size by calling 'kb'

$file->changeMaxSize(300)//the default is 150kb
