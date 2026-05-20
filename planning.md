# Magali: An open tool for the magnetic microscopy community

# Fluxo da apresentação
## Paleomagnetismo
    -  O que é?
        - Pegar definição de alguma citação (Tauxe)
    - Como os minerais são magnetizados?
    - Importância do paleomagnetismo
    - Tipos de grãos
        - Multidomínio
        - Domínio único
        - Pseudo-domínio único
    - Tipos de métodos de medição
        - Spinner
        - Alternating Field (AF)
        - Desmagnetização Térmica
        - Vibrating Sample Magnetometer (VSM)
        - Kappabridge
    - Problemas do paleomagnetismo (conexão com microscopia magnética)
        - Problema clássico: se a amostra tiver muitos grãos MD, o sinal dos grãos SD é "engolido"
        - Limite de detecção
        - Complexidade mineralógica
## Microscopia magnética
    - Apresentar a mudança de paradigma (bulk para escala de grão)
    - Quantum Diamond Microscope (QDM)
        - Temperatura ambiente
        - Explicar como funciona
    - O mapa magnético
        - Não entrega os vetores de magnetização diretamente
        - Componente vertical do campo magnético (bz)
        - Mostrar assinatura do dipolo
        - Mapa raramente tem dipolo prefeito e isolado
            - Múltiplos dipolos aglomerados e sobrepostos com intensidades diferentes
            - Ruído intrumental 
            - Variações de nível de base regionais
        - Mostrar junto ao mapa de MEV
            - Relacionar MEV ao sinal do QDM
    - Nós temos o mapa do campo ($B_z$), mas nós queremos descobrir a fonte que gerou esse campo (justificativa do problema inverso)
        - NÃO SE MEDE MAGNETIZAÇÃO
    - Aproximação ao dipolo
        - Assumimos que cada grão SD pode ser tratado como um dipolo magnético
    - Para cada grão devemos estimar posição (v) e momento magnético (m)
    - Berndt et al. vs Bellon et al.
    - Dificuldades
        - Analisar cada anomalia manualmente?
        - Profundidade difícil de ser estimada
        - Viés humano 
    - Método de Souza-Junior
        - Explicação do método
        - Apresentar diferenças entre os métodos
    - MAGALI
## Desenvolvimento de Software
    - Apresentar o Fatiando a Terra
    - Ciência aberta
    - Mostrar github
    - Falar das dependências
    - Testes
    - Documentação
    - CI/CD


## Sumário
- Paleomagnetismo
- Microscopia magnética
- Métodos
    - Análise do Fluxo de trabalho
    - Fundamentação Teórica
        - Derivadas e TGA
        - Detecção de fontes
        - Estimativa de localização
        - Inversão Linear de momentos magnéticos
    - Desenvolvimento de software
        - Arquitetura e dependências
        - Testes e performace
        - Documentação e exemplos
        - Distribuição e acessibilidade
- Comparação de Performace e Acurácia
    - Método
    - Resultados
- Demonstrção em dados reais de microscopia magnética
- Conclusões