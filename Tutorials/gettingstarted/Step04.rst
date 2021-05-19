Images
======

To display an image, you must first add it to the resource list file.
Create two packages on the Resources folder, one named list, and another
name images, the Structure should look like this:

|image0| 

-  Then go to the **myapp.images.list** and add the file

.. code::

    /images/mj.png:ARGB4444

-  The declaration in the .list file is used in the following format

.. code::

    path:format

-  The path is relative to the resources folder
-  The format is used to specify on what format will be embedded into
   the application

Displaying an image
-------------------

-  to add this image first create and instance of Image widget with the
   path to the image you created

   .. code:: java

       ImageWidget image = new ImageWidget("/images/mj.png");

-  Then, you add a child to the canvas made in Step 3

   .. code:: java

     canvas.addChild(image, 0, 30, Widget.NO_CONSTRAINT, Widget.NO_CONSTRAINT);

-  The final Main.java should look like this

   .. code:: java

       public static void main(String[] args) {
           MicroUI.start();
           Desktop desktop = new Desktop();
           Label label = new Label("Hello World");
           Label label2 = new Label("Hello World 2");

           Canvas canvas = new Canvas();
           canvas.addChild(label, 0, 0, Widget.NO_CONSTRAINT, Widget.NO_CONSTRAINT);
           canvas.addChild(label2, 0, 15, Widget.NO_CONSTRAINT, Widget.NO_CONSTRAINT);

           ImageWidget image = new ImageWidget("/images/mj.png");
           canvas.addChild(image, 0, 30, Widget.NO_CONSTRAINT, Widget.NO_CONSTRAINT);

           CascadingStylesheet css = new CascadingStylesheet();
           EditableStyle style = css.getSelectorStyle(new TypeSelector(Label.class));
           style.setColor(Colors.RED);
           style.setBorder(new RectangularBorder(Colors.BLACK, 1));

           desktop.setStylesheet(css);
           desktop.setWidget(canvas);
           desktop.requestShow();
       }

   |image1| 

.. |image0| image:: resources.png
.. |image1| image:: imagessimulator.png
