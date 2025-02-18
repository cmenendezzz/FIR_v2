# FIR_v2

## Filter Design with T Filter
<img width="813" alt="{D9E46021-2619-40FA-9DE1-4443AA5381BC}" src="https://github.com/user-attachments/assets/59ca4dd6-ac0f-4ba2-9122-8d677fbf0caa" />

<img width="813" alt="{6D8EA0E2-0DC4-409C-9B1F-61BAC0279448}" src="https://github.com/user-attachments/assets/2c3ff73b-5b6f-45d0-b382-a56a7b29fa26" />


## Coefficients
<img width="166" alt="{805D9E2F-63B6-4DE2-A8D9-5C30D86DBE5F}" src="https://github.com/user-attachments/assets/6c7f2207-34ad-4d33-aa5c-703123f7d184" />


 ## Source code 
#ifndef SAMPLEFILTER_H_
#define SAMPLEFILTER_H_

/*

FIR filter designed with
 http://t-filter.appspot.com

sampling frequency: 100000000 Hz

* 0 Hz - 25000000 Hz
  gain = 1
  desired ripple = 5 dB
  actual ripple = 4.05286559576885 dB

* 30000000 Hz - 50000000 Hz
  gain = 0
  desired attenuation = -40 dB
  actual attenuation = -40.25040789635525 dB

*/

#define SAMPLEFILTER_TAP_NUM 21

typedef struct {
  double history[SAMPLEFILTER_TAP_NUM];
  unsigned int last_index;
} SampleFilter;

void SampleFilter_init(SampleFilter* f);
void SampleFilter_put(SampleFilter* f, double input);
double SampleFilter_get(SampleFilter* f);

#endif
