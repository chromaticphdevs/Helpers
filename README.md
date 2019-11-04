# Helpers
PHP BUILT IN HELPERS

#HOW TO USE FILE Helper

//initiate the file helper
$file = new File();
<br/>
$file->setFile($_FILES['uploadFileName'])
->setDIR(YOUR_UPLOAD_PATH) <br/>
->setPrefix('testUpload') //optional<br/>
->upload();

//to check if there is an error do 
<br/>
if(!empty($file->getErrors())) {
 //errors are already imploded so you can use it as string<br/>
 echo $file->getErrors();<br/>
 die();
}else{
  //get the uploaded File name<br/>
  echo $file->getFileUploadName();
}<br/>

//You can add more extension by calling the method<br/>
$file->addFileType('docx') or $file->addFileType(['docx' , 'doc' , 'xlsx'])
//You can also specify the your desired return name of uploaded file by calling
<br/>
$file->setCustomName('uploadName')
<br/>
change the max size by calling 'kb'
<br/>
$file->changeMaxSize(300)//the default is 150kb
