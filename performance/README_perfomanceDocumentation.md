
# 📊 Pruebas de Carga y Estrés con JMeter

Este directorio contiene los archivos necesarios para ejecutar las **pruebas de rendimiento** realizadas con **Apache JMeter**.  
Las pruebas fueron ejecutadas y validadas en **MacOS**, pero tambien agregue instrucciones para ejecutar el archivos .jmx en **Windows**.

---

## 📂 Contenido
- `Camila Performance Testing.jmx` → Plan de prueba en JMeter.
- `run_performance.sh` → Script en Bash para ejecutar pruebas automáticamente (**Mac/Linux**).
- Carpeta `report_YYYYMMDD_HHMMSS` → Reportes HTML generados por JMeter con métricas y gráficas.

---

## ⚙️ Requisitos
1. Instalar **Java 8+**  
   - Verificar con:  
     ```bash
     java -version
     ```

2. Descargar e instalar **Apache JMeter**:  
   👉 [https://jmeter.apache.org/download_jmeter.cgi](https://jmeter.apache.org/download_jmeter.cgi)

3. Añadir JMeter al `PATH` (para poder ejecutarlo desde la terminal o CMD).

---

## ▶️ Ejecución en MacOS / Linux
Las pruebas fueron desarrolladas y ejecutadas en **MacOS**.

### Usando el script automático
En la terminal, desde la carpeta `performance`:
```bash
chmod +x run_performance.sh
./run_performance.sh
```

### Ejecución manual
```bash
jmeter -n -t "Camila Performance Testing.jmx"   -l results_$(date +%Y%m%d_%H%M%S).jtl   -e -o report_$(date +%Y%m%d_%H%M%S)
```

Esto generará:
- Un archivo `.jtl` con los resultados crudos.
- Una carpeta `report_...` con el reporte HTML.

---

## ▶️ Ejecución en Windows
1. Abrir **CMD** o **PowerShell**.
2. Navegar hasta la carpeta `performance` con:
   ```powershell
   cd Desktop\Prueba-Tecnica\performance
   ```
3. Ejecutar:
   ```powershell
   jmeter -n -t "Camila Performance Testing.jmx" -l results.jtl -e -o report
   ```

⚠️ En Windows no se usa `$(date ...)`, por que recomiendo a la persona que revise la prueba cambiar manualmente el nombre de los archivos/carpeta si se quiere conservar múltiples ejecuciones.

---

## 📈 Resultados
El reporte HTML incluye:
- **Throughput (Transacciones por segundo)**  
- **Response Times Over Time (Tiempos de respuesta en el tiempo)**  
- **Error % (Porcentaje de errores)**  
- **Usuarios activos en el tiempo**  

Abrir el archivo:
```
report/index.html
```
en cualquier navegador.

---

## 📝 Nota
✅ Las pruebas las ejecute en Mac el archivo .jmx se puede abrir en windows y correr con jmeter el reporte de fecha y hora solo se puede ver desde mac o linux 
