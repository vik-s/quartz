---
title: Things to pay attention to for a successful RFIC design
tags:
  - circuit
project: substack
date_published: 
status: 🚧
final title:
---
- **Electromagnetics**: Coupling within the RFIC should be taken very carefully into account. Depending on the frequency, every little thing matters. The more effort you put into this, the better your chances of success.  
    
- **Density Fill**: Your chip needs density fill. But this affects circuit performance, and you can't simulate it in any way. You need to have a feel for how far away you should keep density fill from critical components.  
    
- **Device Models:** Transistors models are only so accurate. It is very challenging to have a perfectly accurate model covering DC, small- and large-signal domains (this is what I do at my day-job).  
    
- **Parasitic Extraction**: The routing to the transistors matter, and you can only find its impact via parasitic extraction. You should be careful not to double count anything between device model/extraction/electromagnetics.  
    
- **Packaging**: Ultimately you need to put the chip on a board or package, and this affects the RFIC. It should be taken into account.