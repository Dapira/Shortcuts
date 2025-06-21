<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Atajos de Teclado - Dev Master Cheat Sheet</title>
    <style>
        :root {
            --primary: #00f7ff;
            --secondary: #ff00aa;
            --dark: #0a0a1a;
            --darker: #050510;
            --light: #e0e0ff;
            --neon-glow: 0 0 10px var(--primary), 0 0 20px var(--primary), 0 0 30px var(--primary);
            --neon-glow-secondary: 0 0 10px var(--secondary), 0 0 20px var(--secondary);
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Courier New', monospace;
        }
        
        body {
            background-color: var(--dark);
            color: var(--light);
            background-image: 
                radial-gradient(circle at 20% 30%, rgba(0, 247, 255, 0.1) 0%, transparent 20%),
                radial-gradient(circle at 80% 70%, rgba(255, 0, 170, 0.1) 0%, transparent 20%);
            line-height: 1.6;
            padding: 2rem;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
            border: 1px solid rgba(0, 247, 255, 0.3);
            border-radius: 8px;
            box-shadow: var(--neon-glow);
            background-color: rgba(10, 10, 26, 0.8);
            position: relative;
            overflow: hidden;
        }
        
        .container::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(
                45deg,
                transparent 0%,
                rgba(0, 247, 255, 0.1) 50%,
                transparent 100%
            );
            animation: rotate 20s linear infinite;
            z-index: -1;
        }
        
        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        h1, h2, h3 {
            color: var(--primary);
            margin-bottom: 1.5rem;
            text-shadow: var(--neon-glow-secondary);
        }
        
        h1 {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 2rem;
            position: relative;
            display: inline-block;
            width: 100%;
        }
        
        h1::after {
            content: '';
            display: block;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, transparent, var(--primary), transparent);
            margin-top: 0.5rem;
            box-shadow: var(--neon-glow-secondary);
        }
        
        h2 {
            font-size: 1.8rem;
            margin-top: 2rem;
            border-bottom: 1px solid var(--secondary);
            padding-bottom: 0.5rem;
            display: flex;
            align-items: center;
        }
        
        h2::before {
            content: '❯';
            color: var(--secondary);
            margin-right: 0.5rem;
            text-shadow: var(--neon-glow-secondary);
        }
        
        h3 {
            font-size: 1.4rem;
            color: var(--secondary);
            margin-top: 1.5rem;
        }
        
        .editor-section {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 1.5rem;
        }
        
        .shortcut-card {
            background: rgba(20, 20, 40, 0.7);
            border: 1px solid rgba(0, 247, 255, 0.2);
            border-radius: 6px;
            padding: 1.5rem;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .shortcut-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 247, 255, 0.2);
            border-color: var(--primary);
        }
        
        .shortcut-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(
                135deg,
                transparent 0%,
                rgba(0, 247, 255, 0.05) 50%,
                transparent 100%
            );
            z-index: -1;
        }
        
        .shortcut {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.8rem;
            padding-bottom: 0.8rem;
            border-bottom: 1px dashed rgba(0, 247, 255, 0.3);
        }
        
        .shortcut:last-child {
            margin-bottom: 0;
            padding-bottom: 0;
            border-bottom: none;
        }
        
        .key {
            background-color: var(--darker);
            color: var(--primary);
            padding: 0.3rem 0.6rem;
            border-radius: 4px;
            border: 1px solid var(--primary);
            font-family: monospace;
            font-size: 0.9rem;
            box-shadow: 0 0 5px rgba(0, 247, 255, 0.5);
        }
        
        .description {
            text-align: right;
            flex: 1;
            margin-left: 1rem;
            color: var(--light);
        }
        
        .badge {
            display: inline-block;
            padding: 0.2rem 0.5rem;
            border-radius: 4px;
            font-size: 0.7rem;
            font-weight: bold;
            margin-left: 0.5rem;
            text-transform: uppercase;
        }
        
        .badge-vscode {
            background-color: #007acc;
            color: white;
        }
        
        .badge-sublime {
            background-color: #ff9800;
            color: black;
        }
        
        .badge-atom {
            background-color: #66595c;
            color: white;
        }
        
        .badge-intellij {
            background-color: #000000;
            color: white;
        }
        
        .badge-github {
            background-color: #24292e;
            color: white;
        }
        
        .grid-2 {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 2rem;
        }
        
        .grid-3 {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 2rem;
        }
        
        footer {
            text-align: center;
            margin-top: 3rem;
            padding-top: 2rem;
            border-top: 1px solid rgba(0, 247, 255, 0.3);
            color: var(--light);
            font-size: 0.9rem;
        }
        
        .pulse {
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0% { opacity: 0.7; }
            50% { opacity: 1; }
            100% { opacity: 0.7; }
        }
        
        @media (max-width: 768px) {
            .editor-section, .grid-2, .grid-3 {
                grid-template-columns: 1fr;
            }
            
            body {
                padding: 1rem;
            }
            
            .container {
                padding: 1rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1 class="pulse">⚡ Dev Master Cheat Sheet ⚡</h1>
        <p style="text-align: center; margin-bottom: 2rem; color: var(--secondary);">Atajos de teclado para los editores de código más populares y comandos esenciales de GitHub</p>
        
        <h2>Editores de Código</h2>
        
        <div class="editor-section">
            <div class="shortcut-card">
                <h3>Visual Studio Code</h3>
                <div class="shortcut">
                    <span class="key">Ctrl + P</span>
                    <span class="description">Buscar archivo</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + Shift + P</span>
                    <span class="description">Paleta de comandos</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + `</span>
                    <span class="description">Terminal integrada</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + /</span>
                    <span class="description">Comentar línea</span>
                </div>
                <div class="shortcut">
                    <span class="key">Alt + ↑/↓</span>
                    <span class="description">Mover línea</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + D</span>
                    <span class="description">Seleccionar siguiente coincidencia</span>
                </div>
            </div>
            
            <div class="shortcut-card">
                <h3>Sublime Text</h3>
                <div class="shortcut">
                    <span class="key">Ctrl + P</span>
                    <span class="description">Buscar archivo</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + Shift + P</span>
                    <span class="description">Paleta de comandos</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + L</span>
                    <span class="description">Seleccionar línea</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + Shift + D</span>
                    <span class="description">Duplicar línea</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + /</span>
                    <span class="description">Comentar línea</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + Shift + K</span>
                    <span class="description">Eliminar línea</span>
                </div>
            </div>
            
            <div class="shortcut-card">
                <h3>Atom</h3>
                <div class="shortcut">
                    <span class="key">Ctrl + P</span>
                    <span class="description">Buscar archivo</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + Shift + P</span>
                    <span class="description">Paleta de comandos</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + /</span>
                    <span class="description">Comentar línea</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + Shift + D</span>
                    <span class="description">Duplicar línea</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + Alt + ↑/↓</span>
                    <span class="description">Cursor múltiple</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + G</span>
                    <span class="description">Ir a línea</span>
                </div>
            </div>
            
            <div class="shortcut-card">
                <h3>IntelliJ IDEA</h3>
                <div class="shortcut">
                    <span class="key">Ctrl + N</span>
                    <span class="description">Buscar clase</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + Shift + N</span>
                    <span class="description">Buscar archivo</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + /</span>
                    <span class="description">Comentar línea</span>
                </div>
                <div class="shortcut">
                    <span class="key">Alt + Insert</span>
                    <span class="description">Generar código</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + Alt + L</span>
                    <span class="description">Formatear código</span>
                </div>
                <div class="shortcut">
                    <span class="key">Shift + F6</span>
                    <span class="description">Renombrar</span>
                </div>
            </div>
        </div>
        
        <h2>Navegación y Edición</h2>
        
        <div class="grid-3">
            <div class="shortcut-card">
                <h3>Navegación</h3>
                <div class="shortcut">
                    <span class="key">Ctrl + G</span>
                    <span class="description">Ir a línea</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + F</span>
                    <span class="description">Buscar</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + H</span>
                    <span class="description">Reemplazar</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + Shift + O</span>
                    <span class="description">Ir a símbolo</span>
                </div>
                <div class="shortcut">
                    <span class="key">Alt + ←/→</span>
                    <span class="description">Navegar entre pestañas</span>
                </div>
            </div>
            
            <div class="shortcut-card">
                <h3>Edición</h3>
                <div class="shortcut">
                    <span class="key">Ctrl + D</span>
                    <span class="description">Duplicar línea</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + Shift + K</span>
                    <span class="description">Eliminar línea</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + ]/[</span>
                    <span class="description">Indentar/desindentar</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + Shift + ↑/↓</span>
                    <span class="description">Mover línea</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + Shift + L</span>
                    <span class="description">Seleccionar todas las coincidencias</span>
                </div>
            </div>
            
            <div class="shortcut-card">
                <h3>Multi-cursor</h3>
                <div class="shortcut">
                    <span class="key">Ctrl + Alt + ↑/↓</span>
                    <span class="description">Agregar cursor</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + U</span>
                    <span class="description">Deshacer última operación</span>
                </div>
                <div class="shortcut">
                    <span class="key">Alt + Click</span>
                    <span class="description">Agregar cursor manual</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + Shift + Alt + →</span>
                    <span class="description">Expandir selección</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + Shift + Alt + ←</span>
                    <span class="description">Reducir selección</span>
                </div>
            </div>
        </div>
        
        <h2>Git y GitHub</h2>
        
        <div class="grid-2">
            <div class="shortcut-card">
                <h3>Comandos de Git</h3>
                <div class="shortcut">
                    <span class="key">git init</span>
                    <span class="description">Inicializar repositorio</span>
                </div>
                <div class="shortcut">
                    <span class="key">git clone [url]</span>
                    <span class="description">Clonar repositorio</span>
                </div>
                <div class="shortcut">
                    <span class="key">git status</span>
                    <span class="description">Ver estado</span>
                </div>
                <div class="shortcut">
                    <span class="key">git add .</span>
                    <span class="description">Agregar todos los cambios</span>
                </div>
                <div class="shortcut">
                    <span class="key">git commit -m "mensaje"</span>
                    <span class="description">Hacer commit</span>
                </div>
                <div class="shortcut">
                    <span class="key">git push</span>
                    <span class="description">Enviar cambios</span>
                </div>
                <div class="shortcut">
                    <span class="key">git pull</span>
                    <span class="description">Obtener cambios</span>
                </div>
                <div class="shortcut">
                    <span class="key">git branch</span>
                    <span class="description">Listar ramas</span>
                </div>
                <div class="shortcut">
                    <span class="key">git checkout -b [rama]</span>
                    <span class="description">Crear nueva rama</span>
                </div>
            </div>
            
            <div class="shortcut-card">
                <h3>GitHub Desktop</h3>
                <div class="shortcut">
                    <span class="key">Ctrl + N</span>
                    <span class="description">Nuevo repositorio</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + O</span>
                    <span class="description">Abrir repositorio</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + Shift + C</span>
                    <span class="description">Abrir en línea de comandos</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + P</span>
                    <span class="description">Empujar cambios</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + Shift + P</span>
                    <span class="description">Jalar cambios</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + 1</span>
                    <span class="description">Vista de cambios</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + 2</span>
                    <span class="description">Vista de historial</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + B</span>
                    <span class="description">Lista de ramas</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + Shift + B</span>
                    <span class="description">Crear rama</span>
                </div>
            </div>
        </div>
        
        <h2>Atajos Especiales</h2>
        
        <div class="grid-3">
            <div class="shortcut-card">
                <h3>Depuración</h3>
                <div class="shortcut">
                    <span class="key">F9</span>
                    <span class="description">Alternar punto de interrupción</span>
                </div>
                <div class="shortcut">
                    <span class="key">F5</span>
                    <span class="description">Iniciar/continuar depuración</span>
                </div>
                <div class="shortcut">
                    <span class="key">F10</span>
                    <span class="description">Paso a paso por procedimiento</span>
                </div>
                <div class="shortcut">
                    <span class="key">F11</span>
                    <span class="description">Paso a paso por instrucción</span>
                </div>
                <div class="shortcut">
                    <span class="key">Shift + F5</span>
                    <span class="description">Detener depuración</span>
                </div>
            </div>
            
            <div class="shortcut-card">
                <h3>Terminal</h3>
                <div class="shortcut">
                    <span class="key">Ctrl + `</span>
                    <span class="description">Alternar terminal</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + Shift + `</span>
                    <span class="description">Nueva terminal</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + C</span>
                    <span class="description">Interrumpir proceso</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + L</span>
                    <span class="description">Limpiar terminal</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + ↑/↓</span>
                    <span class="description">Navegar historial</span>
                </div>
            </div>
            
            <div class="shortcut-card">
                <h3>Ventanas</h3>
                <div class="shortcut">
                    <span class="key">Ctrl + B</span>
                    <span class="description">Alternar barra lateral</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + J</span>
                    <span class="description">Alternar panel inferior</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + \</span>
                    <span class="description">Dividir editor</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + 1/2/3</span>
                    <span class="description">Cambiar entre grupos</span>
                </div>
                <div class="shortcut">
                    <span class="key">Ctrl + K, Z</span>
                    <span class="description">Modo zen</span>
                </div>
            </div>
        </div>
        
        <footer>
            <p>✨ Dev Master Cheat Sheet ✨ | Diseño futurista con efectos neón | Actualizado: 2023</p>
            <p style="margin-top: 0.5rem; font-size: 0.8rem; color: var(--secondary);">Presiona Ctrl + P en tu editor para buscar cualquier comando!</p>
        </footer>
    </div>
</body>
</html>
