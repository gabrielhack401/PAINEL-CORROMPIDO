# PAINEL-CORROMPIDO
# COLE NO CONSOLE DEVELOPER DO GOOGLE!
// SCRIPT DE SIMULAÇÃO VISUAL DE HACKING - 15 ABAS FAKE
// Máximo de abas diferentes, 100% visual, local e seguro.

(function() {
    // VARIÁVEL PARA O DATA URI DA IMAGEM (MESMO QUE ANTES): 
    const MATRIX_IMAGE_DATA_URI = 'COLE_AQUI_SEU_DATA_URI_DA_IMAGEM_MATRIX'; 

    // --- 0. Funções de Limpeza e Listagem de IDs ---
    const elementIds = [
        'main-status', 'top-left-decrypt', 'bottom-right-logs', 'top-right-server', 
        'bottom-left-threat', 'mid-left-decoder', 'mid-right-packet', 'top-center-firewall', 
        'bottom-center-alerts', 'mid-left-low-priority', 'mid-right-low-priority',
        'top-mid-left-geo', 'top-mid-right-bandwidth', 'center-info-1', 'center-info-2',
        'scanlines-overlay', 'glitch-border', 'safe-meme-style'
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
        }
    };
    cleanUp();

    // --- 1. Definição da Animação e Estilos Complexos ---
    const styleSheet = new CSSStyleSheet();
    const complexStyles = `
    @keyframes safeShake {
        0%, 100% { transform: translate(1px, 1px) rotate(0deg); } 10% { transform: translate(-1px, -2px) rotate(-1deg); } 90% { transform: translate(1px, 2px) rotate(0deg); }
    }
    @keyframes blink { 0%, 100% { opacity: 1; } 50% { opacity: 0.5; } }
    @keyframes glitch { 0% { transform: translate(0); } 20% { transform: translate(-2px, 2px); } 40% { transform: translate(-4px, -4px); } 60% { transform: translate(4px, 4px); } 80% { transform: translate(2px, -2px); } 100% { transform: translate(0); } }
    .matrix-text-style {
        font-family: 'Consolas', monospace;
        color: #0F0;
        background: rgba(0, 0, 0, 0.95);
        padding: 5px;
        animation: blink 0.3s infinite step-end;
        font-size: 14px;
        border: 2px solid #0F0;
        box-shadow: 0 0 18px rgba(0, 255, 0, 1);
        z-index: 999998;
        text-shadow: 0 0 5px #0F0;
        cursor: pointer;
    }
    #scanlines-overlay {
        position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: 999999;
        pointer-events: none;
        background: repeating-linear-gradient(to bottom, rgba(0, 0, 0, 0.2) 0px, rgba(0, 0, 0, 0.3) 1px, transparent 2px, transparent 3px);
        opacity: 0.7;
    }
    #glitch-border {
        position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: 999990;
        pointer-events: none;
        box-shadow: 0 0 0 5px red, 0 0 0 10px blue, 0 0 0 15px yellow;
        animation: glitch 0.1s infinite alternate;
        opacity: 0.7;
    }`;

    try {
        complexStyles.match(/@keyframes [^{]+\{[^}]+\}/g).forEach((rule, i) => styleSheet.insertRule(rule, i));
        complexStyles.match(/(\.[a-z\-]+|\#[a-z\-]+) [^{]+\{[^}]+\}/g).forEach((rule, i) => styleSheet.insertRule(rule, i + 3));
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
        body.style.filter = 'hue-rotate(100deg) saturate(3) contrast(1.5)';
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
    
    // Efeitos de Tela
    const glitchBorder = createAndAppendElement('glitch-border', '', '');
    const scanlines = createAndAppendElement('scanlines-overlay', '', '');

    const removableElements = [];

    // 1. Centro (Principal)
    const mainStatus = createAndAppendElement(
        'main-status',
        `position: fixed; bottom: 50%; left: 50%; transform: translate(-50%, -50%); padding: 25px; border-radius: 10px; z-index: 999999; animation: safeShake 0.4s infinite;`,
        'SISTEMA INVADIDO: [STATUS: ONLINE]',
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
    
    // --- NOVAS JANELAS PARA COMPLETAR 15 ---

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
    removableElements.forEach(el => {
        el.addEventListener('click', () => {
            cleanUp();
            console.log("Simulação de hacking de 15 janelas removida e estilos restaurados.");
        });
    });
    
    // As caixas de efeito (glitchBorder, scanlines) também precisam ser adicionadas ao array se quiser que o clique nelas funcione,
    // mas como elas não têm 'textContent', o clique nelas só funcionaria se fossem adicionadas ao array 'removableElements'
    // e tivessem 'addEventListener', o que está sendo feito.

    console.log("Simulação MÁXIMA de hacking injetada! Clique em qualquer painel para remover TUDO.");
})();
