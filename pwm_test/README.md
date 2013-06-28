PWM_TEST Driver
========================================

Introduction
----------------------------------------

Contains the files to build the pwm_test driver.

How to build
----------------------------------------
Copy the files into their own directory and type :

    make

Once the build is completed, to load the module type :

    insmod pwm_test.ko

note: You need to rebuild the module each time you change (or rebuild) your kernel.

Alternatively, you can install the module so it will be loaded at boot. Create the pwm directory into
the modules directory :

    mkdir /lib/modules/$(uname -r)/kernel/drivers/pwm

Copy pwm_test.ko to the new directory :

    cp pwm_test.ko /lib/modules/$(uname -r)/kernel/drivers/pwm

Then run :

    depmod

And finally, create a file to tell the kernel to load the module at boot :

    echo "pwm_test" > /etc/modules-load.d/pwm-test.conf

Now, the module will be loaded at boot with modprobe.


