# Balance_Peter
📱 APPLICATION RELEVÉ POIDS RUCHE

Balance Connectée ESP32-C3 + HX711🎯 PROJET COMPLET

Créer un système de pesée de ruche accessible via smartphone, sans Internet, avec historique et graphiques.

📋 MATÉRIEL NÉCESSAIRE

ESP32-C3 SuperMini1 ~2€ AliExpressModule 

HX7111 ~1€ AliExpress Cellules de charge 50kg 4~3€/pièce AliExpress

Batterie LiPo 2000mAh 1~3€ AmazonModule TP4056 (charge) 1~0,50€ AliExpress

Panneau solaire 5V 1W 1~3€ AliExpress

Boîtier étanche1~5€ LocalTotal : ~30-35€ Structure mécanique

Plateau en bois/métal (40x40cm minimum)

Support pour ruche

Protection intempéries

Câblage résistant UV

🔌 SCHÉMA DE CÂBLAGE


              ESP32-C3 SuperMini                 

  GPIO 2  ──→ HX711 DT (Data)                

  GPIO 3  ──→ HX711 SCK (Clock)              

  GPIO 4  ──→ Bouton Tare (+ pull-down 10kΩ

  GPIO 10 ──→ Bouton Relevé (+ pull-down 10kΩ)  

  ADC (GPIO 0) ──→ Batterie (diviseur tension)  

  GND     ──→ Masse commune                     

  3.3V    ──→ HX711 VCC                         

                                    
                  HX711 Module                 

  E+  ──→ Rouge cellules (toutes en parallèle)  

  E-  ──→ Noir cellules (toutes en parallèle)   

  A+  ──→ Blanc cellules (signal+)              

  A-  ──→ Vert cellules (signal-)               


            4 Cellules de charge                 


  Montage en pont de Wheatstone                 

                                              

     [C1]────────[C2]                           

      │           │                              

      │           │                              

     [C3]────────[C4]                           

                                                 

  Toutes rouges ensemble (E+)                   

  Toutes noires ensemble (E-)                   

  Blancs en série → A+                          

  Verts en série → A-                           


              Alimentation                       


  Panneau 5V ──→ TP4056 IN+                     

  Panneau GND ──→ TP4056 IN-                    

  TP4056 BAT+ ──→ LiPo +                        

  TP4056 BAT- ──→ LiPo -                        

  TP4056 OUT+ ──→ ESP32 5V                      

  TP4056 OUT- ──→ ESP32 GND         

