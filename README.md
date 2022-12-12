En balanceProyect ejecutar "npm install"
Copiar Config de Nginx que se encuentra dentro del proyecto

En balanceProyect ejecutar:

pm2 start index.js --name="ServerComun"  --watch -- --PORT=8080
pm2 start index.js --name="cluster" --watch -i 4 -- --PORT=8082
pm2 start index.js --name="infoFork"  --watch -- --PORT=8087        
(No lo ejecuto con -i max por que la computadora que utilizo tiene demasiados hilos para el proyecto)
(Ademas Aclaro que no utilize el Puerto numero 8081 ya que este estaba ocupado en mi computadora que uso para desarrollar
A cambio utilize la 8082 y los 4 puertos a crear para /api/randoms son el [8083,..,8086])
pm2 stop all
pm2 delete all


Para la tarea de Performance Comandos:
npm i -g artillery
npm i autocannon --save
npm i -g 0x
node --prof index.js --PORT=8082
artillery quick --count 50 -n 20 http://localhost:7979/info > result_artillery_info.txt
