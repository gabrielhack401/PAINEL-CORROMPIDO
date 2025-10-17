# PAINEL-CORROMPIDO
# COLE NO CONSOLE DEVELOPER DO GOOGLE!
// SCRIPT DE SIMULAÇÃO VISUAL DE HACKING - TREMORES E PIXELS QUEIMADOS
// Totalmente visual, local e seguro. Extremente intenso.

(function() {
    const MATRIX_IMAGE_DATA_URI = 'COLE_AQUI_SEU_DATA_URI_DA_IMAGEM_MATRIX'; 

    // --- 0. Funções de Limpeza e Listagem de IDs ---
    const elementIds = [
        'main-status', 'top-left-decrypt', 'bottom-right-logs', 'top-right-server', 
        'bottom-left-threat', 'mid-left-decoder', 'mid-right-packet', 'top-center-firewall', 
        'bottom-center-alerts', 'mid-left-low-priority', 'mid-right-low-priority',
        'top-mid-left-geo', 'top-mid-right-bandwidth', 'center-info-1', 'center-info-2',
        'scanlines-overlay', 'glitch-border', 'screen-tremor-overlay', 'pixel-static-overlay', 
        'crt-effect-overlay', 'safe-meme-style'
    ];

    const cleanUp = () => {
        elementIds.forEach(id => {
            const el = document.getElementById(id);
            if (el) el.remove();
        });
        document.adoptedStyleSheets = document.adoptedStyleSheets.filter(s => s && !s.rules[0]?.cssText.includes('@keyframes safeShake'));
        
        const body = document.body;
        if (body.hasAttribute('data-original-style')) {
            body.style.cssText = body.getAttribute('data-original-style');
            body.removeAttribute('data-original-style');
        } else {
            body.style.background = '';
            body.style.filter = ''; 
            body.style.transform = ''; // Remove tremores
            body.style.overflow = ''; // Garante que o overflow seja restaurado
        }
    };
    cleanUp();

    // --- 1. Definição da Animação e Estilos Complexos ---
    const styleSheet = new CSSStyleSheet();
    const complexStyles = `
    @keyframes safeShake { /* Para a caixa principal */
        0%, 100% { transform: translate(1px, 1px) rotate(0deg); } 10% { transform: translate(-1px, -2px) rotate(-1deg); } 90% { transform: translate(1px, 2px) rotate(0deg); }
    }
    @keyframes blink { 0%, 100% { opacity: 1; } 50% { opacity: 0.5; } }
    @keyframes glitch { /* Para a borda principal */
        0% { transform: translate(0); } 20% { transform: translate(-2px, 2px); } 40% { transform: translate(-4px, -4px); } 60% { transform: translate(4px, 4px); } 80% { transform: translate(2px, -2px); } 100% { transform: translate(0); }
    }
    @keyframes screenTremor { /* TREMOR GLOBAL DA TELA */
        0% { transform: translate(1px, 1px); }
        25% { transform: translate(-1px, 0px); }
        50% { transform: translate(0px, 1px); }
        75% { transform: translate(1px, -1px); }
        100% { transform: translate(-1px, 1px); }
    }
    @keyframes pixelStatic { /* Ruído visual de pixel */
        0% { background-position: 0 0; }
        100% { background-position: 100% 100%; }
    }
    .matrix-text-style {
        font-family: 'Consolas', monospace;
        color: #0F0;
        background: rgba(0, 0, 0, 0.9); /* Um pouco menos opaco para ver o fundo Matrix */
        padding: 5px;
        animation: blink 0.2s infinite step-end; /* Cintilação mais rápida */
        font-size: 13px; /* Fonte ligeiramente menor para caber mais */
        border: 2px solid #0F0;
        box-shadow: 0 0 20px rgba(0, 255, 0, 1), inset 0 0 5px rgba(0, 255, 0, 0.5); /* Sombra interna */
        z-index: 999998;
        text-shadow: 0 0 8px #0F0; /* Brilho de texto mais forte */
        cursor: pointer;
        overflow: hidden; /* Para garantir que o conteúdo não vaze */
    }
    /* Efeitos de Tela Base */
    #scanlines-overlay {
        position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: 999999;
        pointer-events: none;
        background: repeating-linear-gradient(to bottom, rgba(0, 0, 0, 0.3) 0px, rgba(0, 0, 0, 0.4) 1px, transparent 2px, transparent 3px);
        opacity: 0.8;
    }
    #glitch-border {
        position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: 999990;
        pointer-events: none;
        box-shadow: 0 0 0 8px red, 0 0 0 16px blue, 0 0 0 24px yellow; /* Bordas mais grossas */
        animation: glitch 0.08s infinite alternate; /* Glitch mais rápido */
        opacity: 0.8;
    }
    /* NOVO EFEITO: Tremor Global da Tela (aplica-se ao body) */
    body {
        animation: screenTremor 0.05s infinite; /* Tremor muito rápido */
        overflow: hidden !important; /* Esconde barras de rolagem causadas pelo tremor */
    }
    /* NOVO EFEITO: Ruído de Pixel / Estática (overlay) */
    #pixel-static-overlay {
        position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: 999999;
        pointer-events: none;
        background-image: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAwCAMAAABg3Am1AAAASFBMVEUAAAD///8AAADLy8vJycnGxsbExMTDw8PCwsLAwMDHx8fPz8/MzMzR0dHT09PS0tLV1dXW1tbZ2dnj4+Pq6urp6enx8fH09PQ/p920AAAAAXRSTlMAQObYZgAAADRJREFUeNpjYBgFo4B+AAEEKwGwgAABBBsAbCAAAIIJgBsIAACCEYAbCAAAgkkA+AAGy5g7QIAAHHlU/8AAAAASUVORK5CYII='); /* Pequeno padrão de ruído */
        background-size: 10px 10px;
        animation: pixelStatic 1s linear infinite; /* Anima o fundo de ruído */
        opacity: 0.1; /* Transparente o suficiente para ser sutil */
        filter: invert(1); /* Inverte cores para efeito de "burn-in" */
    }
    /* NOVO EFEITO: Curvatura e distorção de CRT */
    #crt-effect-overlay {
        position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: 999997;
        pointer-events: none;
        box-shadow: inset 0 0 100px rgba(0,255,0,0.5), inset 0 0 200px rgba(255,0,0,0.3); /* Bordas esmaecidas + burn-in */
        border-radius: 50%; /* Faz a tela parecer curva */
        transform: scale(1.05) perspective(100px) rotateX(2deg) rotateY(2deg); /* Perspectiva para curvatura */
        filter: blur(1px) brightness(1.2); /* Suaviza e intensifica */
        opacity: 0.2;
    }
    `;

    try {
        complexStyles.match(/@keyframes [^{]+\{[^}]+\}/g).forEach((rule, i) => styleSheet.insertRule(rule, i));
        // Ajuste no regex para pegar todos os seletores e suas regras
        const styleRules = complexStyles.split(/@keyframes [^{]+\{[^}]+\}/).slice(1).join('').match(/((\.[a-z\-]+|\#[a-z\-\s]+|body)\s*[^{]+\{[^}]+\})/g);
        if (styleRules) {
            styleRules.forEach((rule, i) => styleSheet.insertRule(rule, i + 5)); // Ajustar o índice base
        }
        document.adoptedStyleSheets = [...document.adoptedStyleSheets, styleSheet];
    } catch (e) {
        const style = document.createElement('style');
        style.type = 'text/css';
        style.id = 'safe-meme-style';
        style.textContent = complexStyles;
        document.head.appendChild(style);
    }
    
    // --- 2. Aplica a tela de fundo (Matrix ou Preto/Verde) ---
    const body = document.body;
    body.setAttribute('data-original-style', body.style.cssText);
    
    if (MATRIX_IMAGE_DATA_URI !== 'COLE_AQUI_SEU_DATA_URI_DA_IMAGEM_MATRIX') {
        body.style.backgroundImage = `url("${MATRIX_IMAGE_DATA_URI}")`;
        body.style.backgroundSize = 'cover';
        body.style.backgroundRepeat = 'repeat';
        body.style.background = '#000';
    } else {
        body.style.background = '#000'; 
        body.style.filter = 'hue-rotate(100deg) saturate(3) contrast(1.5) blur(0.5px)'; // Blur sutil
    }
    
    // --- 3. Criação de Elementos (Função Auxiliar) ---
    const createAndAppendElement = (id, styleText, content, isMemeBox = false) => {
        const el = document.createElement('div');
        el.id = id;
        el.className = isMemeBox ? '' : 'matrix-text-style';
        
        let finalStyle = styleText;
        if (isMemeBox) {
            finalStyle += `background: yellow; color: black; font-family: 'Impact', sans-serif; font-weight: bold; border: 4px solid red; box-shadow: 0 0 30px red; font-size: 35px;`;
        }
        
        el.setAttribute('style', finalStyle.replace(/\s+/g, ' '));
        el.textContent = content;
        document.body.appendChild(el);
        return el;
    };

    // --- 4. 15 Janelas de Simulação + Efeitos de Tela ---
    
    // Efeitos de Tela Principais (camadas de efeito)
    const glitchBorder = createAndAppendElement('glitch-border', '', '');
    const scanlines = createAndAppendElement('scanlines-overlay', '', '');
    const pixelStatic = createAndAppendElement('pixel-static-overlay', '', ''); // Novo
    const crtEffect = createAndAppendElement('crt-effect-overlay', '', ''); // Novo

    const removableElements = [];

    // 1. Centro (Principal)
    const mainStatus = createAndAppendElement(
        'main-status',
        `position: fixed; bottom: 50%; left: 50%; transform: translate(-50%, -50%); padding: 25px; border-radius: 10px; z-index: 999999; animation: safeShake 0.4s infinite;`,
        'SISTEMA CRÍTICO: FALHA DE KERNEL',
        true
    );
    removableElements.push(mainStatus);


    // --- Cantos ---
    // 2. Topo Esquerdo (Decriptação)
    removableElements.push(createAndAppendElement(
        'top-left-decrypt', `position: fixed; top: 10px; left: 10px; width: 300px; white-space: pre-wrap;`,
        `\n>> DECRYPTING: 0x4B3C...\n>> KEY FOUND: F8A79B\n>> ACCESS LEVEL: ADMIN\n>> LOGGING USER: TRACE COMPLETE\n`
    ));

    // 3. Fundo Direito (Logs)
    removableElements.push(createAndAppendElement(
        'bottom-right-logs', `position: fixed; bottom: 10px; right: 10px; width: 300px; height: 160px; overflow: hidden; white-space: pre-wrap;`,
        `\n[TASK] Protocols initialized.\n[TASK] Bypassing firewall: Success!\n[ERROR] Connection instability.\n[STATUS] Transfer rate: 99.9%\n`
    ));
    
    // 4. Topo Direito (Status do Servidor)
    removableElements.push(createAndAppendElement(
        'top-right-server', `position: fixed; top: 10px; right: 10px; width: 250px; white-space: pre-wrap;`,
        `\nSERVER STATUS:\n\nCPU: 98% (High)\nMEM: 65% (Normal)\nTEMP: 75°C (CRITICAL)\n`
    ));

    // 5. Fundo Esquerdo (Mensagem de Ameaça Fake)
    removableElements.push(createAndAppendElement(
        'bottom-left-threat', `position: fixed; bottom: 10px; left: 10px; width: 300px; white-space: pre-wrap; border-color: red; color: red;`,
        `\n!!! WARNING !!!\n\n[KERNEL PANIC] - DATA WIPE INITIATED.\n[Click to end the simulation.]`
    ));
    
    // --- Laterais ---
    // 6. Central Esquerda (Decodificação de Dados)
    removableElements.push(createAndAppendElement(
        'mid-left-decoder', `position: fixed; top: 35%; left: 5px; width: 280px; white-space: pre-wrap;`,
        `\n-- DATA DECODER --\n\n0xABF27 | Decrypted\n0x19C0E | Failed\n0x5D4A2 | Decrypting...\n0x9F3B1 | Decrypted\n`
    ));

    // 7. Central Direita (Monitoramento de Pacotes)
    removableElements.push(createAndAppendElement(
        'mid-right-packet', `position: fixed; top: 35%; right: 5px; width: 280px; white-space: pre-wrap;`,
        `\n-- PACKET MONITOR --\n\n> TCP: PUSH from 1.1.1.1\n> UDP: ACK to 8.8.8.8\n> ICMP: PING FAILED\n> ARP: REQUEST Sent\n`
    ));

    // --- Topo e Fundo Central ---
    // 8. Topo Central (Status do Firewall)
    removableElements.push(createAndAppendElement(
        'top-center-firewall', `position: fixed; top: 5%; left: 50%; transform: translateX(-50%); width: 400px; white-space: pre-wrap; border-color: yellow; color: yellow;`,
        `\n--- FIREWALL STATUS ---\n\nRule 45: BLOCKED\nRule 12: BYPASSED\nRule 99: ACTIVE\n\n[ALL SYSTEMS COMPROMISED]\n`
    ));

    // 9. Fundo Central (Alertas de Segurança)
    removableElements.push(createAndAppendElement(
        'bottom-center-alerts', `position: fixed; bottom: 5%; left: 50%; transform: translateX(-50%); width: 450px; white-space: pre-wrap; border-color: red; color: red;`,
        `\n!!! SECURITY ALERT LEVEL 5 !!!\n\n> UNKNOWN THREAD INITIATED\n> LOCATION: UNTRACEABLE\n> ACTION: MANUAL INTERVENTION REQUIRED\n`
    ));
    
    // --- Mais Janelas para Completar 15 ---

    // 10. Central Esquerda (Baixa Prioridade) - Abaixo da 6
    removableElements.push(createAndAppendElement(
        'mid-left-low-priority', `position: fixed; top: 60%; left: 5px; width: 280px; white-space: pre-wrap;`,
        `\n-- LOW PRIORITY LOG --\n\n[IDLE] Running background scans.\n[IDLE] Checking system clock.\n[IDLE] Garbage collection.\n`
    ));

    // 11. Central Direita (Baixa Prioridade) - Abaixo da 7
    removableElements.push(createAndAppendElement(
        'mid-right-low-priority', `position: fixed; top: 60%; right: 5px; width: 280px; white-space: pre-wrap;`,
        `\n-- NETWORK DIAGNOSTIC --\n\nLatency: 5ms\nJitter: 0.1ms\nError Rate: 0.00%\n\n[Connection Stable]\n`
    ));

    // 12. Abaixo da 2 (Topo Esquerdo)
    removableElements.push(createAndAppendElement(
        'top-mid-left-geo', `position: fixed; top: 20%; left: 10px; width: 250px; white-space: pre-wrap;`,
        `\n--- GEO LOCATION ---\n\nTARGET: UNKNOWN\nREGION: INACCESSIBLE\nSIGNAL: ENCRYPTED\n`
    ));

    // 13. Abaixo da 4 (Topo Direito)
    removableElements.push(createAndAppendElement(
        'top-mid-right-bandwidth', `position: fixed; top: 20%; right: 10px; width: 250px; white-space: pre-wrap;`,
        `\n--- BANDWIDTH MONITOR ---\n\nIN: 15.2 Mbps\nOUT: 0.8 Mbps\nAVG: 7.0 Mbps\n`
    ));

    // 14. Perto do Centro (Info 1)
    removableElements.push(createAndAppendElement(
        'center-info-1', `position: fixed; top: 40%; left: 35%; width: 200px; white-space: pre-wrap; border-color: blue; color: blue;`,
        `\n--- SESSION INFO ---\n\nProtocol: SSH\nCipher: AES-256\nSTATUS: ACTIVE\n`
    ));
    
    // 15. Perto do Centro (Info 2)
    removableElements.push(createAndAppendElement(
        'center-info-2', `position: fixed; bottom: 40%; right: 35%; width: 200px; white-space: pre-wrap; border-color: yellow; color: yellow;`,
        `\n--- FILE EXTRACT ---\n\nFILE: 10/15\nBUFFER: 80%\nETA: 00:05s\n`
    ));


    // --- 5. Configuração de Limpeza Final ---
    // Adiciona o evento de clique para remover TUDO em todos os elementos injetados
    // Adiciona também os overlays para que o clique em qualquer lugar remova tudo
    removableElements.push(glitchBorder, scanlines, pixelStatic, crtEffect);

    removableElements.forEach(el => {
        el.addEventListener('click', () => {
            cleanUp();
            console.log("Simulação de hacking de cinema removida e estilos restaurados.");
        });
    });

    console.log("Simulação de hacking de CINEMA com efeitos de tela queimada injetada! Clique em qualquer painel para remover TUDO.");
})();
