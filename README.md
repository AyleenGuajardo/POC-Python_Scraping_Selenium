<h1 align ="center"> 🖨️ Contador de Impresiones Automático </h1>

¡Hola! 👋 Este script en Python está diseñado con mucho cariño para automatizar la extracción de conteos de impresión desde múltiples impresoras Ricoh utilizando Selenium y peticiones cURL, y generar un reporte en Excel con toda la info que necesitas. 🧾✨
<br>
Ideal para ejecutarlo automáticamente al final de cada mes (sí, se puede montar en Docker y programar con cron 😉).

<body>
<h3>🚀 ¿Qué hace este script?</h3>

<ul>
  <li>📥 Lee una lista de direcciones IP de impresoras desde un archivo ips.txt.</li>
  <li>🧠 Se conecta a cada impresora vía Selenium.</li>
  <li>🔒 Inicia sesión de forma automática.</li>
  <li>📊 Extrae el hostname y estados de los componentes.</li>
  <li>🔃 Utiliza curl para descargar el archivo de contador de usuarios (en CSV).</li>
  <li>📚 Convierte los datos a un archivo Excel con toda la info organizada.</li>
  <li>🚫 Registra los errores de cada impresora (incluyendo “Conexión rechazada” o “La autenticación ha fallado”).</li>
  <li>🎯 ¡Todo esto de forma silenciosa en segundo plano (headless)!</li>
</ul>

<h3>🧰 Requisitos</h3>

<ul>
  <li>Python 3.9+</li>
  <li>Google Chrome o Edge</li>
  <li>Chromedriver o Edgedriver</li> 
  
</ul>  
<h6>(Asegúrate que las versiones sean compatibles)</h6>
<h6>👀¡OJO! Está programado en función de que el user admin sea el mismo para todas las máquinas</h6>

<h3>Debes instalar las siguientes librerías:</h3>
<ul>
  <li>selenium </li>
  <li>pandas </li>
  <li>openpyxl</li>
</ul>

<h3>📁 Estructura esperada</h3>

<p>
ContadorImpresora/ <br>
│ <br>
├── contador_impresoras.py          <br>
├── ips.txt                         <br>
├── reporte_impresiones_XX.xlsx     <br>
└── README.md                       <br>
</p>


<h3>📝 ¿Cómo usarlo?</h3>
<ul>
  <li>Clona o copia este proyecto en tu máquina.</li>
  <li>Asegúrate de que chromedriver esté en la ruta correcta (CHROMEDRIVER_PATH).</li>
  <li>Llena el archivo ips.txt con las IPs de las impresoras que quieres procesar.</li>
</ul>

<h3>Ejecuta el script:</h3>
<ul>
  <li>python contador_impresoras.py</li>
  <li>Revisa el Excel generado en tu carpeta de descargas 🥳</li>
</ul>

<h3>🐞 ¿Qué pasa si una impresora falla?</h3>

No te preocupes, el script:

Continúa con la siguiente impresora.

Anota el error específico en la columna “Estado Impresora”.

Si el error es de autenticación, te dice “Alert: La autenticación ha fallado”.

Si es un problema de conexión, te dice “Conexión rechazada”.

Así puedes revisar qué IPs necesitas mirar con más calma.

<h3>🐳 ¿Lo quieres automatizar con Docker?</h3>

<h6>Sí, puedes. Aquí te dejo una idea básica: </h6>

<ul>
  <li>Crea un Dockerfile.</li>
  <li>Usa un cron dentro del contenedor para que se ejecute al final de cada mes.</li>
  <li>Monta un volumen para guardar los reportes.</li>
</ul>

<h2>¡Y listo! Automatizado al 100%!</h2>
  
</body>

____________________________________________________________________________________________________________________________________________________
Desarrollado con ❤️ por <a href="https://www.instagram.com/ayleencgi/" target="_blank">
  <img src="https://github.com/user-attachments/assets/70d78bad-21f0-4fd7-9de9-86ece0620a9d" alt="instagram" width="16" height="16" style="vertical-align: middle;"/>
  ayleencgi
</a>. Inspirado en la necesidad de automatizar tareas repetitivas.
