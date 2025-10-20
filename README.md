# HeliosSecurityCenter

**Contato:** [devhansoft@gmail.com](mailto:devhansoft@gmail.com)  
**Licença:** Software proprietário — HANSoft License  

---

## Descrição Geral
O **Helios Security Center (HSC)** combina **criptografia avançada** e **arquitetura de proteção multicamadas** para proteger arquivos e dados sensíveis.

### Principais Defesas
- Criptografia híbrida (AES + ChaCha20)  
- HMAC-SHA256 para integridade e autenticação  
- Ofuscação e particionamento de chaves  
- Inserção aleatória de bytes e codificação personalizada  
- Bloqueio temporário contra ataques de força bruta  
- Autolimpeza de dados em memória protegida  

---

## Módulos Principais

### **[ TEXTO ] — Criptografia de Texto**
Cria mensagens criptografadas seguras para comunicação protegida e flexível.

---

### **[ COFRE ] — Criptografia de Arquivos**
Protege qualquer tipo de arquivo (documentos, imagens, vídeos, etc.), convertendo o conteúdo em dados ilegíveis sem a senha correta.  
Ideal para **discos locais, pendrives e nuvem**.

---

### **[ ESTEG ] — Esteganografia com Criptografia**
Realiza a inserção de dados criptografados nos bits menos significativos (LSB)
dos pixels de uma imagem. Cada canal de cor (R, G, B) armazena um bit de
informação sem causar alterações visíveis.

Os dados ficam embutidos dentro da estrutura dos pixels, o que torna sua detecção
extremamente difícil, mesmo por meio de análise forense ou comparação visual.

**Vantagens:**
- Dificulta detecção visual/forense  
- Ideal para mensagens pequenas  
- Mantém autenticidade da imagem  

**Desvantagens:**
- Capacidade limitada a resolução da imagem (pixels)
- Processamento mais lento, pois trabalha bit a bit dentro dos pixels

**Considerações:**
A imagem final será no formato PNG, pois esse formato é sem perdas (lossless) e
preserva os valores exatos dos pixels ao salvar.

- Respeite a capacidade de ocultação de dados de cada imagem indicada no status;
- Quanto maior a resolução da imagem (pixels), maior a capacidade de ocultação;
- Ao selecionar JPEG ou outro formato, o programa converterá para PNG.

---

### **[ CONTAINER ] — Concatenação de Arquivos com Criptografia**
Oculta um arquivo dentro de outro (imagem, vídeo, áudio, PDF, etc.)  
sem afetar a funcionalidade do arquivo base.

O arquivo base permanece íntegro e funcional, enquanto o conteúdo oculto
fica protegido por múltiplas camadas de segurança e só pode ser recuperado
com a chave correta.

Formatos seguros como BASE:
- PNG, JPG, JPEG, SVG, TIFF  (imagens)
- MP4, AVI, MOV, WMV         (vídeos)
- MP3, WAV, FLAC             (áudio)
- PDF                        (documentos)

**Observação:**  
Evite usar como BASE formatos que validam estrutura interna:
- ZIP, RAR, 7Z, DOCX, XLSX (serão corrompidos ao receber dados extras)

O arquivo OCULTO pode ter qualquer extensão.

**Vantagens:**
- Suporta arquivos grandes (sem limite prático) 
- O arquivo base continua totalmente funcional  
- Rápido (opera byte a byte)

Nota:
A concatenação pode ser detectada por análise forense, pois adiciona bytes extras ao final do arquivo base, mas todo o conteúdo permanece criptografado e ilegível, garantindo privacidade mesmo sob inspeção.

---

## Avisos de Segurança
- Utilize senhas fortes (mínimo 12 caracteres);
- Combine letras maiúsculas, minúsculas, números e símbolos;
- Teste a decriptografia logo após a criptografia;
- Mantenha backups dos arquivos originais;
- Cuidado com os meios de envio e armazenamento;
- Erros podem ocorrer devido a falhas do sistema;
- O desenvolvedor não se responsabiliza por perda ou acesso indevido de dados.

---

## ⚖️ Aviso Legal
Este software é fornecido "no estado em que se encontra" ("as is"),
sem garantias de qualquer tipo, expressas ou implícitas.

O desenvolvedor não se responsabiliza por quaisquer danos,
perdas de dados ou outros problemas decorrentes do uso deste programa.

Ao utilizar este aplicativo, você reconhece e aceita os termos acima.
