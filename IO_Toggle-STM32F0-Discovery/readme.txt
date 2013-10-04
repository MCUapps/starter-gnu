/**
  @page IO_Toggle GPIO IO Toggle example
  
  @verbatim
  ******************** (C) COPYRIGHT 2012 STMicroelectronics *******************
  * @file    IO_Toggle/readme.txt  
  * @author  MCD Application Team
  * @version V1.0.0
  * @date    23-March-2012
  * @brief   GPIO IO Toggle example Description.
  ******************************************************************************
  *
  * Licensed under MCD-ST Liberty SW License Agreement V2, (the "License");
  * You may not use this file except in compliance with the License.
  * You may obtain a copy of the License at:
  *
  *        http://www.st.com/software_license_agreement_liberty_v2
  *
  * Unless required by applicable law or agreed to in writing, software 
  * distributed under the License is distributed on an "AS IS" BASIS, 
  * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  * See the License for the specific language governing permissions and
  * limitations under the License.
  *   
  ******************************************************************************
   @endverbatim

@par Example Description 

GPIO ports are connected on AHB bus, using BSRR and BRR registers two cycles is
required to set a pin and another two cycles to reset it. So GPIO pins can toggle
at AHB clock divided by 4.

This example describes how to use BSRR and BRR (Port Bit Set/Reset Register High 
and Low) for maximum IO toggling.

PC8 and PC9 when using the STM32F0-Discovery Kit(configured in output pushpull mode)
toggles in a forever loop:
 - Set PC8 and PC9 by setting corresponding bits in BSRR register
 - Reset PC8 and PC9 by setting corresponding bits in BRR register

In this example, HCLK is configured at 48 MHz so PC8 and PC9 toggles at 12MHz.
To achieve the maximum IO toggling frequency, you have to configure your compiler
options for high speed optimization.


@par Directory contents 

  - IO_Toggle/stm32f0xx_conf.h    Library Configuration file
  - IO_Toggle/stm32f0xx_it.c      Interrupt handlers
  - IO_Toggle/stm32f0xx_it.h      Interrupt handlers header file
  - IO_Toggle/main.c              Main program
  - IO_Toggle/system_stm32f0xx.c  STM32F0xx system source file
  
@note The "system_stm32f0xx.c" file contains the system clock configuration for
      STM32F0xx devices, and is customized for use with STM32F0-Discovery Kit. 
      The STM32F0xx is configured to run at 48 MHz, following the three  
      configuration below:
        + PLL_SOURCE_HSI
           - HSI (~8 MHz) used to clock the PLL, and the PLL is used as system 
             clock source.  
        + PLL_SOURCE_HSE          
           - HSE (8 MHz) used to clock the PLL, and the PLL is used as system
             clock source.
           - The HSE crystal is not provided with the Discovery Kit, some 
             hardware modification are needed in manner to connect this crystal.
             For more details, refer to section "4.7 OSC clock" in "STM32F0 discovery kit User manual (UM1525)"
        + PLL_SOURCE_HSE_BYPASS   
           - HSE bypassed with an external clock (fixed at 8 MHz, coming from 
             ST-Link circuit) used to clock the PLL, and the PLL is used as 
             system clock source.
           - Some  hardware modification are needed in manner to bypass the HSE 
             with clock coming from the ST-Link circuit.
             For more details, refer to section "4.7 OSC clock" in "STM32F0 discovery kit User manual (UM1525)"
      User can select one of the three configuration in system_stm32f0xx.c file
      (default configuration is PLL_SOURCE_HSI).
         

@par Hardware and Software environment

  - This example runs on STM32F0xx Devices.
  
  - This example has been tested with STMicroelectronics STM32F0-Discovery (MB1034) 
    RevB and can be easily tailored to any other supported device and development board.


@par How to use it ? 

In order to make the program work, you must do the following :

 + EWARM
    - Open the IO_Toggle.eww workspace 
    - Rebuild all files: Project->Rebuild all
    - Load project image: Project->Debug
    - Run program: Debug->Go(F5)

 + MDK-ARM
    - Open the IO_Toggle.uvproj project
    - Rebuild all files: Project->Rebuild all target files
    - Load project image: Debug->Start/Stop Debug Session
    - Run program: Debug->Run (F5)    

 + TASKING
    - Open TASKING toolchain.
    - Click on File->Import, select General->'Existing Projects into Workspace' 
      and then click "Next". 
    - Browse to  TASKING workspace directory and select the project "IO_Toggle"   
    - Rebuild all project files: Select the project in the "Project explorer" 
      window then click on Project->build project menu.
    - Run program: Select the project in the "Project explorer" window then click 
      Run->Debug (F11)

 + TrueSTUDIO for ARM
    - Open the TrueSTUDIO for ARM toolchain.
    - Click on File->Switch Workspace->Other and browse to TrueSTUDIO workspace 
      directory.
    - Click on File->Import, select General->'Existing Projects into Workspace' 
      and then click "Next". 
    - Browse to the TrueSTUDIO workspace directory and select the project "IO_Toggle" 
    - Rebuild all project files: Select the project in the "Project explorer" 
      window then click on Project->build project menu.
    - Run program: Select the project in the "Project explorer" window then click 
      Run->Debug (F11)

 * <h3><center>&copy; COPYRIGHT STMicroelectronics</center></h3>
 */
