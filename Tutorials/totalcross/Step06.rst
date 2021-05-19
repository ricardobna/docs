Event Handling
==============

Events are handled in the same \* Using the code created on the Last
Step, it's possible to simply add the onClick Listener

.. code:: java

    button.setOnClickListener(new OnClickListener() {
        @Override
        public void onClick() {
            System.out.println("Clicked!");
        }
    });

This should be shown in the console

.. code:: Console

    =============== [ Initialization Stage ] ===============
    =============== [ Converting fonts ] ===============
    =============== [ Converting images ] ===============
    The watchdog is not configured by the application, so it is enabled. This default behavior will reset the MCU after ~32 seconds of not executing the RTOS idle task
    =============== [ Launching on Simulator ] ===============
    Clicked!
    Clicked!
    Clicked!
    Clicked!
    Clicked!

Previous
~~~~~~~~

Next
~~~~

