# ⚡ ToqueQR — Pago Móvil Venezolano en Un Solo Toque

![Android](https://img.shields.io/badge/Android-8.0%2B%20(API%2026)-10B981?style=for-the-badge&logo=android&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-Jetpack%20Compose%20120FPS-06B6D4?style=for-the-badge&logo=kotlin&logoColor=white)
![Open Source](https://img.shields.io/badge/Open%20Source-Zero--Backend-F59E0B?style=for-the-badge)
[![Portafolio Drako](https://img.shields.io/badge/Portafolio-drakostore.xyz-8B5CF6?style=for-the-badge&logo=vercel&logoColor=white)](https://drakostore.xyz/about)

**ToqueQR** (`ve.org.toqueqr`) es una aplicación Android **100% Open Source** y **Zero-Backend** diseñada para generar y escanear códigos QR de **Pago Móvil** en Venezuela de forma instantánea, sin registro, sin servidores intermedios y con auto-rellenado nativo en las aplicaciones bancarias.

🌐 **Web Oficial y Descarga APK:** [https://toqueqr.unaux.com](https://toqueqr.unaux.com)  
👑 **Fundador y Creador:** **Drako** (`@DrakoCodex` — *Único Fundador*)  
💼 **Portafolio Oficial:** [https://drakostore.xyz/about](https://drakostore.xyz/about)

---

## 🚀 Arquitectura del Protocolo ToqueQR (3 Capas)

1. **Codificación QR Ultraligera (Offline-First):**
   * Empaqueta la **Línea Bancaria Directa**: `{codigo_banco} {telefono} {cedula_rif} {monto_con_coma}` (ej. `0102 04125558910 V18456789 545,00`).
   * Genera un QR menos denso en `< 0.3 ms`, 100% funcional sin internet y compatible con el portapapeles inteligente de **BDVApp**, **BanescoMóvil**, **BNC** y **Bancamiga**.
2. **Copiado Inteligente + Lanzador de App Bancaria en 1 Toque:**
   * Copia la línea bancaria formateada al portapapeles y abre al instante la app del banco pagador (`com.bdvenlinea`, `com.banesco.banescomovil`, `com.mercantilbanco.mercantilmovil`, `com.bbva.provincial`, `com.bnc.bncapp`, `com.bancamiga.bancamigamovil`).
3. **Auto-Rellenado Nativo (`AccessibilityService`) y Pago por SMS (`smsto:`):**
   * **`ToqueAutoFillService`:** Ventana de seguridad de **45 segundos** tras escanear un QR; detecta los campos `EditText` de Teléfono, Cédula/RIF y Monto en la app bancaria e inyecta los datos con `ACTION_SET_TEXT`.
   * **Pago por SMS sin Internet:** Comandos pre-armados para **BDV (`2661`)**, **Banesco (`2846`)**, **Mercantil (`24024`)** y **Provincial (`2662`)**.

---

## ✨ Características Principales

* **Interfaz FinTech Dark a 120 FPS:** Construida en Jetpack Compose con teclado numérico bimonetario propio (`FastAmountNumpadSheet`) y divisor de cuentas entre amigos.
* **Tasas en Vivo con Respaldo Offline:** Sincronización de **Dólar BCV ($)**, **Euro BCV (€)** y **USDT Paralelo (₮)**.
* **3 Perfiles Locales:** Alterna con un toque entre **Personal**, **Negocio** y **Delivery** guardados únicamente en `SharedPreferences`.
* **Catálogo de los 21 Bancos:** Buscador interactivo con todos los bancos de Pago Móvil de Venezuela.
* **Generador de Habladores PNG HD (`1200x1760 px`):** Exporta carteles listos para imprimir o compartir en 4 temas (`CYBER`, `CYAN`, `LIGHT`, `GOLD`).

---

## 🛠️ Compilación en Android Studio

1. Clona este repositorio:
   ```bash
   git clone [https://github.com/DrakoCodex/toqueqr.git](https://github.com/DrakoCodex/toqueqr.git)
