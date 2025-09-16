# Choosing your required virtual machine (VM) configuration

Once logged in, you will be taken to the **Virtual Machines** (VM) page where you can start a new machine or connect to an existing one.  
![Virtual Machine options](../images/getting-started-as-a-new-user/virtual-machine-options.png)
You will be offered a variety of virtual machine types.  
!!! warning
    Choose the Basic machine unless a script requires high memory or increased CPU capacity, and is ready to go. Test your script on the Basic machine first, as other options are more expensive.  

!!! note
    Some machine types have many CPUs, which are suitable for multithreaded applications like plink or regenie that can fully utilise them. These applications may sometimes run input/output operations too quickly for standard Google bucket storage, requiring you to copy key files to faster local storage (see below).

## Choosing a custom machine configuration

It is possible you may require a Virtual Machine that offers resources different to the standard flavors i.e. higher-memory, higher-cpu or memory-optimised instances. You can choose a custom VM configuration from the **Virtual Machines** page by expanding the **Use custom Virtual Machine profile** section at the bottom.  
![Custom Virtual Machine profile](../images/getting-started-as-a-new-user/custom-virtual-machine-profile.png)

!!! warning
    Choose the Use custom Virtual Machine profile only when absolutely necessary, use Basic machine unless a script requires high memory or increased CPU capacity. Excess use of higher-spec machines can significantly impact running costs. Test your script on the Basic machine first, as other options are more expensive.

## Switching off the machine

Your virtual machine will keep running for 24 hours if you are doing nothing. You can disconnect from Chrome or Firefox (the reccommended browsers for the TRE), turn your laptop off, and then you will be straight back into the exact same machine when you connect again (within 24h). If you have Linux jobs running, the machine will keep going while these run (however long) plus another 48h.  
!!! warning
    Keeping machines running in the background costs money. So please actively shutdown (if you do not need the extra 48h) using the "Off" button on the bottom of the side menu or the `Shut down` option in the `Applications` menu.

![The 'Off' button](../images/getting-started-as-a-new-user/the-off-button.png)
![The 'Shut down' option](../images/getting-started-as-a-new-user/the-shutdown-option.png)
