# ATmega32-AVR-ADC-Driver
Highly Configurable Software Driver

This driver allows you to easily use the ADC Module (10-bits resolution) for **Analog** to **Digital** conversions in the Atmel AVR ATmega32 Microcontroller.

The initialization function of the ADC Software Driver takes input parameters as configurations for the ADC Module.

These configuration are as follows:-
------------------------------------

The selection is implemented by choosing from the following enumerations as input paramaters to the initiallization function.
 
 -> ADC_Voltage_Reference: 
    AREF_PIN, AVCC, RESERVERED, INTERNAL_VOLTAGE.
  
 -> ADC_Result_Adjustment:
    RIGHT_ADJUST, LEFT_ADJUST.
    
 -> ADC_Prescaler_Division_Factor:
    	  DIV_BY_2,
	  DIV_BY_4,
	  DIV_BY_8,
	  DIV_BY_16,
	  DIV_BY_32,
	  DIV_BY_64,
	  DIV_BY_128.
 
 -> ADC_Auto_Trigger_Source:
          FREE_RUNNING_MODE,
	  ANALOG_COMPARATOR,
	  EXTENAL_INTERRUPT_REQUEST_0,
	  TIMER_COUNTER_0_COMPARE_MATCH,
	  TIMER_COUNTER_0_OVERFLOW,
	  TIMER_COUNTER_1_COMPARE_MATCH_B,
	  TIMER_COUNTER_1_OVERFLOW,
	  TIMER_COUNTER_1_CAPTURE_EVENT.
    
 
The structure which will be passed by address to the initialization function is called "ADC_Config_Type".

**************************************************************************************************************
EXAMPLE: ADC_Config_Type Config_Ptr = {AVCC, RIGHT_ADJUST, DIV_BY_8, EXTENAL_INTERRUPT_REQUEST_0};
ADC_init(&Config_Ptr);
**************************************************************************************************************


The union "ADC_Analog_Channel_Type" will also be passed by address, but to another function (ADC_readChannel_Polling/ADC_readChannel_Interrupts)

*************************************************************************
EXAMPLE: ADC_Analog_Channel_Type Channel_Config_Ptr = {ADC1};
ADC_readChannel_Interrupts(&Channel_Config_Ptr);
*************************************************************************




