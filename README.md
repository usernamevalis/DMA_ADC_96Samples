README.md

This is a simple ADC - TIM2 using dma program.
I struggled forever with getting the readings to happen continuously.
For whatever reason (if anyone knows), the adc reading conversion cycle only happens once if the sample time is below 48:


	ADC_RegularChannelConfig(ADC1, ADC_Channel_18, 1, ADC_SampleTime_48Cycles)

48 plus seems to work fine.

I had a similar problewhen i was sampling the ADC and withou DMA but in that instance i could not get the adc to work without 
adding a prescaler to the ADC:

ADC_CommonInitStructure.ADC_Prescaler = ADC_Prescaler_Div2;

it changes nothing in this case though, still just curious as to what it could be. cleraly something to do with timing