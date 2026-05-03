# dio-azure5
Arquitetura Azure

Componentes da arquitetura do Azure
Regiões disponíveis variam os preços, conforme regras e impostos locais.
60 regiões, mais de 140 países.
As regiões são compostas de um ou mais datacenters muito próximos - conectados entre si.
Eles fornecem flexibilidade e escala para reduzir a latência do cliente.
regiões preservam a residencia dos dados com uma oferta abrangente de conformidade.

Pares de região
no mínimo 300 milhas de separação entre pares de regiões
replicação automática para alguns serviços
recuperação de região priorizada em caso de interrupção
as atualizações são distribuídas sequencialmente

Curiosamente a região par do Brasil (sul do Brasil) é o Centro - Sul dos EUA
Regiões soberanas do Azure: instancia separada do Azure, exclusiva ao Governo dos EUA.
Na China, a Microsoft foi o primeiro provedor estrangeiro de serviço de nuvem pública e é fisicamente separada dos serviços, operado pela 21ViaNet - com todos os dados dentro da China.
Recursos do Azure

**No Microsoft Azure, um “recurso” é qualquer serviço ou componente que você cria e gerencia na nuvem (como máquinas virtuais, bancos de dados, redes virtuais, contas de armazenamento). Esses recursos precisam estar organizados dentro de um “grupo de recursos”, e a regra é clara: cada recurso só pode existir em um único grupo de recursos por vez

VM - virtual machine
contas de armazenamento
redes virtuais
serviços de aplicativos
banco de dados SQL
funções: São os blocos fundamentais que compõem suas soluções na nuvem.

grupos de recursos
Web + BD, VM, armazenamento - em um grupo
um grupo de recursos é um conteiner que voce usa para gerenciar e agregar recursos em uma única unidade.
Ciclo de vida: É recomendado colocar no mesmo grupo os recursos que compartilham o mesmo ciclo de vida (implantação, atualização e exclusão).

Se você criar uma máquina virtual, ela estará vinculada a um único grupo de recursos.
Para reorganizar, é possível mover o recurso para outro grupo ou até para outra assinatura, mas nunca duplicá-lo em múltiplos grupos.
Benefício: Evita confusão e garante que cada recurso tenha um escopo único de gerenciamento.
Em resumo: recursos são os serviços que você cria no Azure, e cada um deles só pode pertencer a um único grupo de recursos. Essa estrutura é essencial para manter organização, governança e controle de custos na nuvem.

Assinaturas do Azure
uma conta pode ter várias assinaturas diferentes - desenvolvimento, teste e produção.
uma fatura por assinatura.
essa pode ser uma estratégia para dividir custos por projeto
rlatórios de cobrança e faturas separados para cada assinatura, assim como possibilidade de limitar o controle de acesso

Grupos de gerenciamento (Management Groups)

São o nível mais alto da hierarquia.
Permitem organizar várias assinaturas do Azure sob uma mesma estrutura administrativa.
Úteis para aplicar políticas e controles de governança em larga escala.
Assinaturas (Subscriptions)

Cada assinatura representa um contrato de uso do Azure, com limites de cobrança e acesso.
Dentro de uma assinatura, você pode criar diversos grupos de recursos.
É o ponto onde se controla custos e faturamento.
Grupos de recursos (Resource Groups)

São contêineres lógicos que agrupam recursos relacionados.
Servem para organizar e gerenciar recursos que compartilham ciclo de vida.
Cada recurso só pode pertencer a um único grupo de recursos.
Recursos (Resources)

São os elementos finais: máquinas virtuais, bancos de dados, contas de armazenamento, redes virtuais, etc.
Eles são criados dentro de um grupo de recursos e não podem existir fora dele.
Ícones na imagem (computador, banco SQL, engrenagens) representam exemplos desses recursos.
Em resumo: a imagem mostra que no Azure tudo começa em grupos de gerenciamento, que contêm assinaturas, que por sua vez contêm grupos de recursos, e dentro deles estão os recursos. Essa estrutura garante organização, governança e controle eficiente.

Passo a passo básico no Portal Azure

Entrar no Portal AzureAcesse portal.azure.com e faça login com sua conta.
Selecionar “Grupos de recursos”No menu lateral, clique em Grupos de recursos.
Em seguida, clique em Criar.
Preencher informações obrigatóriasAssinatura: escolha a assinatura do Azure onde o grupo será criado.
Nome do grupo de recursos: insira um nome único e descritivo (ex.: Dev-Test, Prod-DB).
Região: selecione a localização (ex.: Brazil South ou East US).Essa região define onde os metadados do grupo serão armazenados.
Os recursos dentro do grupo podem estar em outras regiões, mas é recomendável escolher a mesma região para simplificar a gestão.
Revisar e criarClique em Examinar + criar.
Confirme os dados e selecione Criar.
Confirmar criaçãoEm poucos segundos o grupo estará disponível.
Você pode acessá-lo pela lista de grupos de recursos ou pela notificação exibida no topo do portal
