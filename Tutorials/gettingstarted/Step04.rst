Images
======

To display an image, you must first add it to the resource list file.
Create two packages on the Resources folder, one named list, and another
name images, the Structure should look like this:

|image0| 

-  Then go to the **myapp.images.list** and add the file

.. code::

    /images/mj.png:ARGB4444

-  The image declaration in the .list file follows this pattern:

.. code::

    path:format

-  ``path`` is the path to the image file, relative to the ``resources`` folder.
-  ``format`` specifies how the image will be embedded in the application.

Displaying an image
-------------------

- To display this image, first create an instance of the widget ``ImageWidget``, specifying the path to the image in the consructor:

   .. code:: java

       ImageWidget image = new ImageWidget("/images/mj.png");

- Add the widget to the canvas container by adding this line to the ``main`` of your application:

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
