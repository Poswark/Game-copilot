# Prompt para Crear Juego DevOps Runner

## Contexto
Necesito que crees un juego de navegador completo inspirado en el juego del dinosaurio de Chrome, pero con temática de DevOps.

## Objetivo Principal
Crear un juego web funcional donde un desarrollador (representado como un robot) debe saltar obstáculos y responder preguntas de DevOps.

---

## Especificaciones Técnicas

### Tecnologías Requeridas
- HTML5 Canvas para renderizado
- JavaScript vanilla (ES6+)
- CSS3 para estilos
- Sin dependencias externas

### Arquitectura de Archivos
Crea exactamente **4 archivos**:

1. **index.html** - Estructura HTML y canvas
2. **styles.css** - Estilos visuales y responsive design
3. **game.js** - Toda la lógica del juego
4. **README.md** - Documentación de instalación y uso en español

---

## Mecánicas del Juego

### Gameplay Básico
- **Personaje**: Robot desarrollador que puede saltar
- **Obstáculos**: Herramientas de software (Ansible, Terraform, Docker, Kubernetes, Jenkins)
- **Objetivo**: Evitar los obstáculos saltando sobre ellos
- **Controles**: Desktop (Espacio/Flecha Arriba), Móvil (Tap)

### Sistema de Preguntas (Característica Principal)
- **Frecuencia**: Cada 15 segundos de juego activo
- **Tipo**: Preguntas de respuesta múltiple sobre DevOps
- **Mecánica**: 
  - El juego se pausa al mostrar la pregunta
  - Si acierta: continúa el juego
  - Si falla: Game Over
- **Temas**: CI/CD, contenedores, infraestructura como código, monitoreo, automatización
- **Exactamente 7 preguntas**

### Power-ups
- **Debug Token**: Ralentiza el juego por 5 segundos
- **Aparición**: Aleatoriamente cada 20-30 segundos

### Sistema de Puntuación
- **Puntos por obstáculo evitado**: +10
- **Puntos por pregunta correcta**: +50
- **Mostrar**: Score actual, High Score y racha actual
- **Persistir** High Score en localStorage

### Progresión de Dificultad
- **Velocidad inicial**: moderada
- **Incremento**: +2% cada 10 segundos
- **Mayor frecuencia** de obstáculos con el tiempo
- **Patrones más complejos** de aparición

### Easter Egg
- **Activación**: Al alcanzar 500 puntos
- **Efecto**: "Code Review Jetpack" - permite volar sobre obstáculos por 10 segundos
- **Visual**: Animación especial del robot con jetpack

---

## Requisitos de Implementación

### Game Loop
```javascript
// Debe usar requestAnimationFrame para 60 FPS
function gameLoop(timestamp) {
    update(deltaTime);
    render();
    requestAnimationFrame(gameLoop);
}
```

### Sistema de Colisiones
- Implementar detección por bounding boxes (AABB)
- Verificar colisiones entre jugador y obstáculos
- Verificar recolección de power-ups

### Física del Salto
- Gravedad realista (acelera hacia abajo)
- Velocidad de salto inicial
- Límite de saltos (solo desde el suelo)

### Controles
- **Desktop**: Barra espaciadora o flecha arriba para saltar
- **Móvil**: Tap en la pantalla para saltar
- **Responsive** y adaptativo

### Optimización de Rendimiento
- Remover obstáculos y power-ups fuera de pantalla
- Pool de objetos para evitar crear/destruir constantemente
- Evitar memory leaks
- Precarga de assets

### Diseño Visual
- **Estilo**: Pixel art / retro 8-bit
- **Colores**: Paleta tech (azul, verde neón, negro, blanco)
- **Animaciones**: Suaves y responsive
- **Canvas responsive**: Ajustar a window.devicePixelRatio

---

## Preguntas de DevOps (Incluir exactamente 7)

Incluir exactamente 7 preguntas sobre: CI/CD, Docker, Kubernetes, Git, contenedores, monitoreo, IaC.

Ejemplo:
- ¿Qué significa CI/CD?
- ¿Cuál es el puerto por defecto de Docker?
- ¿Qué herramienta NO es de IaC?
- Y 4 preguntas más...

---

## Estructura del README.md

Debe incluir:
- Título y descripción del juego
- Características principales
- Cómo jugar (controles)
- Instalación (abrir index.html)
- Tecnologías usadas
- Estructura de archivos
- Créditos/Autor

---

## Criterios de Éxito

### Funcionalidad
- ✅ El juego carga sin errores
- ✅ El personaje salta correctamente
- ✅ Los obstáculos se mueven y detectan colisiones
- ✅ Las preguntas aparecen cada 5 segundos
- ✅ El sistema de puntuación funciona
- ✅ El High Score se guarda en localStorage

### Calidad de Código
- ✅ Código modular y organizado
- ✅ Comentarios en funciones clave
- ✅ Sin errores en consola
- ✅ Sin memory leaks
- ✅ Rendimiento estable a 60 FPS

### UX/UI
- ✅ Controles responsivos
- ✅ Interfaz clara e intuitiva
- ✅ Feedback visual al usuario
- ✅ Funciona en móvil y desktop

---

## Instrucciones de Entrega

Crea los 4 archivos siguiendo todas las especificaciones anteriores. El juego debe ser completamente funcional y cumplir con todos los criterios de éxito.

---

## Notas Adicionales

- Prioriza funcionalidad sobre gráficos complejos
- Usa emojis o caracteres Unicode si no tienes imágenes
- El código debe ser autocontenido (sin dependencias externas)
- Comenta las secciones complejas del código
- Asegúrate de que el canvas escale correctamente en diferentes pantallas

---

**Comienza creando los 4 archivos siguiendo estas especificaciones.**