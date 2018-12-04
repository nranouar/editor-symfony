# editor-symfony
How to create and add editor text for a project symfony 

step 1 :
  create project with framework symfony or to have an existing symfony project

step 2 :
  add two library in symfony project in public or web folder : 

     => the first library is CKEditor < https://ckeditor.com/ > - download here : < https://ckeditor.com/ckeditor-4/download/ > and to choose the standard package or full package
     
     => the seconde library is KCFinder : < https://kcfinder.sunhater.com/ > - download here : < https://kcfinder.sunhater.com/integrate >

Now, you must integrate KCFinder in CKEditor :

  1 ) add in CKEditor/config.js
  
     config.filebrowserBrowseUrl = '/kcfinder/browse.php?opener=ckeditor&type=files';
     config.filebrowserImageBrowseUrl = '/kcfinder/browse.php?opener=ckeditor&type=images';
     config.filebrowserFlashBrowseUrl = '/kcfinder/browse.php?opener=ckeditor&type=flash';
     config.filebrowserUploadUrl = '/kcfinder/upload.php?opener=ckeditor&type=files';
     config.filebrowserImageUploadUrl = '/kcfinder/upload.php?opener=ckeditor&type=images';
     config.filebrowserFlashUploadUrl = '/kcfinder/upload.php?opener=ckeditor&type=flash';
     
   2 ) change permission in KCFinder/conf/config.php

        OLD => 'disabled' => true   ||||   NEW  => 'disabled' => false,
        
   
   3 ) Finaly add code for your html code :
      - first step add library CKEditor with code :
         <script src="{{ asset('ckeditor/ckeditor.js') }}"></script>
      - second setp to establish the connection between the textarea field and the library with an id attribute 

          <textarea name="editor" id="editor" rows="10" cols="80">
            This is my textarea to be replaced with CKEditor.
          </textarea> 
          
          <script>
            CKEDITOR.replace( 'editor' );
          </script>


   4 ) start your project with port 80 obligatorily
