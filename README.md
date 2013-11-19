# Bootstrap 3 + WYSIHTML5 + Multi Image Upload

This is a working example for a combination of

* [Bootstrap](http://getbootstrap.com/) 3 by Twitter – an amazing front-end framework,
* [WYSIHTML5](https://github.com/xing/wysihtml5) by XING – a rich-text editor producing HTML5 code without the enormousness of CKEditor, TinyMCE or similar, and
* [jQuery File Upload](https://github.com/blueimp/jQuery-File-Upload) by blueimp – allowing multi-file uploads with upload status (without Flash, of course).

This repository is inspired by [bassjobsen/wysihtml5-image-upload](https://github.com/bassjobsen/wysihtml5-image-upload/), which is based on Bootstrap 2 and jQuery.upload v1.0.2 (by lagoscript, 2010). Thanks guys for a great repository to get started with.

My version also includes [fabiopaiva/bootstrap3-wysihtml5](https://github.com/fabiopaiva/bootstrap3-wysihtml5.git) as submodule to bring Bootstrap 3 and WYSIHTML5 together.

> Note: Although bootstrap3-wysihtml5 includes a full copy of Bootstrap 3.0.0 (at the time of writing), I included Bootstrap 3.0.2 via CDN, because 3.0.0 has a few visible bugs.


## What Can You Do With this Repository?

See this repository as an example, not as a ready-to-use plugin for your own project.

You will be able to normally use the WYSIWYG editor, click on the *insert image* button of the toolbar to open a [modal](http://getbootstrap.com/javascript/#modals), upload one or more images at the same time.

As soon as an image is uploaded, a thumbnail will be added to a list of uploaded files, ready to be insert into the editor. Each thumbnail has it's own *remove* button.

The *insert* button of the modal changes its status from normal (clickable) to disabled, depending on the availability of uploaded images and even indicates the number of images that will be insert when clicked (e.g. "Insert 2 images").

If an upload fails, a Bootstrap alert message will be displayed.

If you click in insert button, all uploaded pictures that have not been removed will be insert into the editor.

> Note: Uploaded images will never be deleted from the server. You'll have to take care of that yourself.


## How to Install this Example?

If you want to install this example on your own server, download or clone this repository (including the submodules). There is not a lot of configuration required, just a few things:

You will need a server-sided upload handler. Luckily, jQuery-File-Upload comes with a few (PHP, NodeJS, Google App Engine…?). I have only used PHP and it worked straight away. You will find them in the directory `jquery-file-upload/server`. If you're **not** using PHP, you'll have to change the URL of `data-url` (this is where files will be uploaded to) in the file `wysihtml5-image-upload.js`:

```html
<input id="fileupload" type="file" name="files[]" data-url="jquery-file-upload/server/php/" multiple>
```

You will also have to make sure the web server has write permissions to the folder where the upload handler wants to store files. In case you're using the included PHP handler, you might have to change permissions like so:

```
chmod 0777 jquery-file-upload/server/php/files
```


## How to Use this in Your Own Project?

If you want to use this kind of functionality in your own project, I recommend you download and install this example as described above and then copy and modify the parts as required. I'm sorry that I can't provide a ready-to-use installation module. Everybody will have their own requirements.

As a basic recipe, you will need:

* Bootstrap 3 (I recommend 3.0.2 at the time of writing)
* WYSIHTML5
* jQuery-File-Upload
* your own upload handler
* your own version of `wysihtml5-image-upload.js` (which itself is a modified version of `bootstrap3-wysihtml5/src/bootstrap3-wysihtml5.js`)
* some CSS (just look into `index.html` to find out what you need or don't need)

You should also make sure that you delete unused files from upload directory, or better move files that are actually in use (e.g. in blog articles) to a permanent folder and clear the temporary upload folder on a regular basis…

Enjoy!