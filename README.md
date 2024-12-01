# Anotações Az-900

## Módulo 1 - Conceitos
### O que é computação em nuvem
é o fornecimento de serviços de computação pela internet, permite provisionamento rápido, recursos flexíveis e economias de escala.

### Benefícios da Nuvem
- alta disponibilidade
- escalabilidade (ajusta recursos - horizontal)
- elasticidade (ajusta conforme o uso - vertical)
- confiabilidade (resiliência)
- previsibilidade (confiança no desempenho e custo)
- segurança (a nuvem fornece as ferramentas, mas o usuário é responsável por implementar)
- governança (padrões e requisitos regulatórios)
- gerenciabilidade (portal, linha de comando, powershell)

### Modelos de nuvem
- **Nuvem privada** - a organização é controle total pelos serviços e é responsável pela manutenção e atualizações de hardware.
- **Nuvem pública** - pertence a um provedor que permite o acesso à internet através de uma conexão segura.
- **Nuvem híbrida** une nuvem pública e privada, mantendo a comunicação entre elas. É um modelo flexível.
As organizações escolhem onde executar os aplicativos, controlam segurança, conformidade e requisitos legais.
### Custo de capital (Capex) vc Custo Operacional (Opex)
**Despesas de capital:** Gasto em infraestrutura. A despesa inicial é alta e reduz com o tempo.
**Despesa Operacional:** Gasto em produtos e serviços, pago conforme o uso. 

### Serviços de Nuvem
**IaaS** - servidores e armazenamento. Servço mais flexível: você configura e gerencia seu aplicativo.
**PaaS** - ferramentas para desenvolvedores, análise de negócio, gerenciamento de database. O gerenciamento da infraestrutura é realizado pelo provedor.
**SaaS** - aplicativos e apps. Pago conforme o uso (modelo assinatura)

## Módulo 2 - Arquitetura e Serviços
Para criar ou usar serviços do Azure, é necessário uma assinatura do Azure.
A partir de uma assinatura, você poderá criar os grupos de recursos. Para comprar um acesso ao azure:
- diretamente no site do Azure
- através de parceiros de Soluções em Nuvem
- através de parceiros da Microsoft

Tipos de conta:
Conta gratuita: acesso gratuito a produtos populares por 12 meses, crédito a ser usado nos primeiros 30 dias e acesso a mais de 25 produtos sempre gratuitos.
Conta de estudante: acesso a determinados produtos por 12 meses, crédito a ser usado nos 12 primeiros meses, acesso a determinadas ferramentas para desenvolvedores de software.

### Infraestrutura Física
**Datacenters** - são agrupados em regiões do azure ou em zonas de disponibilidade, projetados para obter resiliência e confiabilidade para as cargas de trabalho.

- **Região** - é uma área geográfica do planeta que contém pelo menos um datacenter.
obs. alguns recursos estão disponíveis em somente determinadas regiões.
Serviços que não requerem região específica: Azure Active Directory, Gerenciador de Tráfego do Azure e DNS do Azure

- **Pares de região** - As regiões estão emparelhadas a outra região com aproximadamente 300 milhas de distância. Isso garante redundância de região.
obs. A replicação deve ser feita pelo cliente.

- **Região soberana** - São instâncias isoladas da Azure: Região Governamental dos EUA e Azure Chine (21via)

- **Zonas de disponibilidade** - são datacenters separados fisicamente dentro de uma região Azure. Cada zona é composta por um ou mais datacenters equipados por energia, resfriamento e rede independente. Elas estão conectadas por meio de redes de fibra óptica privada de alta velocidade.

Destinadas a VMs, discos gerenciados, balanceadores de carga e bancos de dados SQL, e oferecem os seguintes serviços: 

- Serviços em zonas: recurso em uma zona específica (por exemplo, VMs, discos gerenciados, endereços IP).
- Serviços com redundância de zona: a plataforma replica automaticamente entre zonas. 
- Serviços não regionais: os serviços estão sempre disponíveis em geografias do Azure e são resilientes a interrupções em toda a zona, bem como a interrupções em toda a região.

### Infraestrutura de Gerenciamento
**Grupo de Gerenciamento** - fornece gerenciamento corporativo em larga escala, indapendente do tipo de assinatura existente. Gerencia o acesso, as políticas e conformidade das assinaturas. Aplica condições de governança.
obs. Uma árvore do grupo de gerenciamento pode dar suporte a até 6 níveis de profundiade.

**Assinatura** - é uma unidade lógica de gerenciamento, cobrança e escala.
A assinatura fornece acesso autenticado e autorizado a serviços e produtos do Azure. É vinculada a uma conta do Azure (identidade no Microsoft Entra ID)
Uma conta pode ter várias assinaturas.

**Grupo de Recursos** - agrupamento de recursos.
quando uma ação é aplicada ao grupo de recursos, todos os recursos sofrem esta ação.

**Recurso** - bloco de construção básico do Azure. VM, redes virtuais, banco de dados, serviços.

### Serviços de computação
#### Computação e Rede
Serviço sob demanda que fornece recursos de computação, como discos, processadores, memória, redes e sistemas operacionais. 

**Máquinas Virtuais (VMs)** fornecem Iaas na forma de servidor virtualizado. - é preciso configurar, atualizar e manter o software executado na VM.

Conjuntos de dimensionamento (escala) de máquinas virtuais - cria e gerencia grupo de VMs idênticas com balanceamento de carga. Permite a centralização do gerenciamento destas máquinas.

Conjuntos de disponibilidade da máquina virtual - ajuda a criar um ambiente mais resiliente e altamente disponível.
obs. até 3 domínios de falha, sem custo adicional

**Área de Trabalho Virtual do Azure** - serviço de virtualização de área de trabalho e aplicativos, executado na nuvem. 

**Conteiners** - ambiente leve e virtualizado que não exige gerenciamento do sistema operacional e responde a alterações sob demanda.

**Instância de Contêiner** - oferta PaaS. Executa pod de conteiner.

**Aplicativos de Conteiner** - modelo PaaS - instâncias de conteiner para balancear carga e escalar

**Kubernetes** - serviço de orquestração para contêiners em arquiteturas distribuídas.

**Azure Function** - Paas - Código baseado em eventos, executado sem exigir infraestrutura. Com base da demanada.

**Serviço de Aplicativo Azure** - você pode hospedar os estilos mais comuns de serviço de aplicativos, como:

- Aplicativos Web -  suporte completo para a hospedagem de aplicativos Web usando ASP.NET, ASP.NET Core, Java, Ruby, Node.js, PHP ou Python
- Aplicativos de API - criar APIs Web baseadas em REST usando a linguagem e a estrutura que você quiser.
- WebJobs - para executar um script (.cmd, .bat, PowerShell ou Bash) ou um programa (.exe, Java, PHP, Python ou Node.js) 
- Aplicativos móveis -para criar rapidamente um back-end para aplicativos iOS e Android.

#### Redes

#### Armazenamento

#### Identidade, acesso e segurança

