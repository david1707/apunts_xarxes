Antigament, cada dispositiu tenia uns protocols decidits per cada empresa. Açò feia que la interoperabilitat fos complicada, en el millor dels casos.

La ISO (International Organisation for Standardization) va crear un model standard basat en capes i que funcionés per a tothom, creant així la interoperabilitat entre diferents proveïdors. 

Aquest model té [[Model OSI - Capes|7 capes]], cadascuna independent de les altres.

![[model_osi.png]]

Açò permet tindre un standard que garanteix la interoperabilitat, un desenvolupament independent entre capes (Algú fent una aplicació en PHP no necessita saber els detalls de com funcionen els cables d'internet o un router, tot i que la seua aplicació utilitze internet), 

**Cada capa del model OSI només es comunica amb elements de la mateixa capa.**

## Comunicació entre dispositius

Quan dos dispositius es comuniquen, l'acció va de la capa 7 a la capa 1 del primer dispositiu, i de la capa 1 a la capa 7 del dispositiu que rep l'acció.

Per exemple, un usuari envia informació des de la capa 7, o Aplicació. La capa 7 afegeix (meta)informació al que es transmet en el header. Al arribar a la capa 6, aquesta també afegeix més (meta)informació al header, i així fins arribar a la capa 2 (En la capa 2 s'afegeix un **FCS** o Frame Check Sequence, que s'assegura que la informació no ha patit cap corrupció).

![[Encapsulació.png]]

En el dispositiu que rep aquesta informació, el procés és invertit mitjançant el procés de Des-encapsulació, fins que només queda la informació original. 

