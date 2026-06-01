# Memòria Tècnica del Projecte NEXUS

## 1. Introducció
Aquesta memòria tècnica descriu la proposta de solució per al projecte NEXUS, orientat a la implementació d’una plataforma d’aprenentatge en línia (e-learning). L’objectiu principal és definir, justificar i validar una infraestructura tecnològica eficient, escalable i sostenible.

---

## 2. Presentació de la consultoria
L’equip encarregat del projecte està especialitzat en:
Infraestructures web  
Plataformes e-learning  
Optimització de rendiment i sostenibilitat  

Disposem d’experiència en entorns virtuals educatius, oferint solucions fiables i mantenibles.

---

## 3. Context i necessitats del client (NEXUS)

### 3.1 Necessitats principals
Plataforma e-learning estable i escalable  
Rendiment òptim amb múltiples usuaris simultanis  
Cost ajustat i controlat  
Manteniment senzill  
Sostenibilitat  

### 3.2 Problemàtica
El repte consisteix en:
Seleccionar un servidor web eficient  
Escollir un LMS fiable  
Integrar la solució en un VPS  

---

## 4. Anàlisi del servidor web

### 4.1 Opcions avaluades
Apache  
Nginx  

### 4.2 Comparativa

| Característica | Apache | Nginx |
|--------------|--------|--------|
| Instal·lació | Guiada i amigable | Ràpida i lleugera |
| Configuració | Intuïtiva | Centralitzada |
| Rendiment | Webs dinàmiques | Alta concurrència |
| Consum | 80–100 MB | 20–30 MB |
| Temps resposta | ~0.20 s | ~0.09 s |
| Escalabilitat | Limitada | Alta |

### 4.3 Conclusions
Nginx ofereix:
Millor rendiment
Menor consum de recursos
Major escalabilitat

### 4.4 Decisió
**Servidor web seleccionat: Nginx**

---

## 5. Anàlisi de la plataforma LMS

### 5.1 Opcions analitzades
Moodle  
Canvas LMS  

### 5.2 Comparativa

| Característica | Moodle | Canvas |
|--------------|--------|--------|
| Tipus | Codi obert | Plataforma moderna |
| Instal·lació | Senzilla | Complexa |
| Personalització | Alta | Limitada |
| Comunitat | Gran | Menor |
| Consum | 512MB – 1GB | ~8GB |

### 5.3 Experiència pràctica
**Moodle**: fàcil, estable i intuïtiu  
**Canvas**: problemes de compatibilitat i requisits elevats  

### 5.4 Conclusions
Canvas és potent però no adequat per VPS limitats.

### 5.5 Decisió
**Plataforma seleccionada: Moodle**

---

## 6. Integració de la solució

### 6.1 Arquitectura final
VPS Linux  
Nginx  
PHP  
MariaDB  
Moodle  
Certificat SSL (Let’s Encrypt)  

### 6.2 Característiques
Sistema escalable  
Optimitzat per rendiment  
Entorn segur  

---

## 7. Viabilitat tècnica i econòmica

### 7.1 Infraestructura
2 vCPU  
4 GB RAM  
80 GB SSD  

### 7.2 Cost estimat
**8 € – 15 € / mes**

### 7.3 Manteniment
1–2 hores mensuals  
Actualitzacions  
Còpies de seguretat  

---

## 8. Sostenibilitat (Green IT)
Nginx redueix el consum energètic  
Moodle optimitza la càrrega  
VPS escalable evita recursos innecessaris  
Sistema pensat per llarga durabilitat  

---

## 9. Resultats
La solució compleix:
Plataforma estable i escalable  
Bon rendiment  
Cost controlat  
Manteniment senzill  
Sostenibilitat  

---

## 10. Conclusions
La solució final seleccionada és:

**Nginx** com a servidor web  
**Moodle** com a plataforma e-learning  
**VPS optimitzat** com a infraestructura  

Aquesta combinació garanteix una solució eficient, econòmica i validada en entorns reals.
