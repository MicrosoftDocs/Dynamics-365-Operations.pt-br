---
title: Novidades ou alterações no Dynamics 365 for Operations versão 1611 (novembro de 2016)
description: Este tópico descreve os recursos novos ou alterados no Dynamics 365 for Operations versão 1611.
author: sericks007
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom: 221294
ms.assetid: 357931ed-f843-4bf5-bc85-0da3de0619ec
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 0625010143b7df9c3c897bf7f43ef25993303240
ms.sourcegitcommit: 03fa7556840aa59f825697f6f9edeb58ea673fca
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "7752799"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-operations-version-1611-november-2016"></a>Novidades ou alterações no Dynamics 365 for Operations versão 1611 (novembro de 2016)

[!include [banner](../includes/banner.md)]

Este tópico descreve os recursos novos ou alterados no  Dynamics 365 for Operations versão 1611.

## <a name="cost-accounting"></a>Contabilização de custos

<table>
<thead>
<tr>
<th>O que você pode fazer</th>
<th>Por que isso é importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>Definir dimensões de elemento de custo e importar membros de dimensões de elemento de custo.</td>
<td>Elementos de custo são usados na contabilização de custos para categorizar custos e documentar o fluxo de custos. Os elementos de custo primários são importados por meio de um conector de dados do Microsoft Dynamics 365 for Operations para obtenção de contas principais diretamente do Operations ou por meio de um conector de dados genérico, no qual as contas primárias são obtidas via Microsoft Excel de qualquer tipo de sistema de origem. Após as contas principais serem importadas na contabilização de custos, elas são usadas como membros de dimensões de elementos de custo. Os elementos de custo secunDiários são definidos pelo usuário e usados em alocações para documentar o fluxo de custos.</td>
</tr>
<tr>
<td>Mapear dimensões de elementos de custo.</td>
<td>Se as contas principais de suas entidades legais não puderem ser compartilhadas por causa de requisitos contábeis estatutários, você poderá mapeá-las depois de importá-las para a Contabilização de custos para obter uma visão global da organização.</td>
</tr>
<tr>
<td>Definir dimensões de objeto de custo e importar membros de dimensões de objeto de custo.</td>
<td>Objetos de custo são qualquer tipo de objeto para os quais os custos são atribuídos. Os objetos de custo típicos incluem produtos, projetos, recursos, departamentos, centros de custo e regiões geográficas. Você pode usar um conector de dados do Microsoft Dynamics 365 for Operations para obter valores e dimensões financeiras do Operations ou usar um conector de dados genérico, no qual você pode obter dimensões e valores por meio do Excel de qualquer tipo de sistema de origem. Por exemplo, se você usar a dimensão financeira do centro de custos como a dimensão de objeto, todos os centros de custos importados serão os membros da dimensão para o objeto de custo.</td>
</tr>
<tr>
<td>Definir ou importar dimensões estatísticas.</td>
<td>Membros de dimensões estatísticas são medidos em unidades não monetárias, como horas, número de funcionários e quadras. São usados em demonstrativos ou como base para alocações e distribuições.</td>
</tr>
<tr>
<td>Criar modelos de provedor de medidas estatísticas.</td>
<td>Um modelo de provedor de medidas estatísticas é usado para transformar dados do Dynamics 365 for Operations em medidas estatísticas. Depois, o modelo é associado a um determinado membro de dimensões estatísticas. Os modelos são pré-filtrados para que mostrem apenas tabelas associadas às dimensões financeiras.</td>
</tr>
<tr>
<td>Criar razões de contabilização de custos.</td>
<td>Um razão de contabilização de custos é um razão agnóstico que usa calendário e moeda próprios. Desempenha um importante papel no processamento de todas as transações de custo. Por exemplo, um razão de contabilização de custos classifica custos com base em seus próprios elementos de custo e custos agregados baseados em suas próprias dimensões de objeto. Você pode criar quantos razões de contabilização de custos forem necessários para fazer relatórios de gerenciamento de várias perspectivas.</td>
</tr>
<tr>
<td>Criar unidades de controle de custos.</td>
<td>Unidades de controle de custos compõem a estrutura de custos e definem o fluxo de custos em um razão de contabilização de custos. Elas devem ser associadas a dimensões de objetos de custo para representar as dimensões de objetos de custo no razão.</td>
</tr>
<tr>
<td>Processar entradas de contabilidade.</td>
<td>Para medir o desempenho real, é necessário ter dados. Os dados serão importados por meio dos conectores que você define para o razão da contabilização de custo. Ao processar as entradas da contabilidade, os dados são importados de forma incremental.</td>
</tr>
<tr>
<td>Processar entradas de orçamento.</td>
<td>Para medir o desempenho de orçamento, você deve ter dados. Os dados serão importados por meio dos conectores que você define para o razão da contabilização de custo. Ao processar as entradas de orçamento, os dados são importados de forma incremental.</td>
</tr>
<tr>
<td>Criar e aplicar políticas de comportamento de custos.</td>
<td>Você utiliza uma política de comportamento de custos para classificar custos como fixos, variáveis ou semivariáveis. Uma política é baseada em regra e efetiva por data. Por padrão, todos os custos são marcados como não classificados até você aplicar uma política de comportamento de custos e calcular os efeitos da regra. Após o cálculo, os custos são classificados.</td>
</tr>
<tr>
<td>Rastrear custos.</td>
<td>Para ajudar a entender o impacto das políticas de custo, a contabilização de custos permite que você rastreie custos até os valores de origem e regras aplicadas onde elas se originam. Essa funcionalidade fornece completa rastreabilidade de quando os custos ocorreram, que tipos de custos ocorreram e quais são as regras de comportamento de custos aplicadas.</td>
</tr>
<tr>
<td>Definir hierarquias de dimensão.</td>
<td>Você pode criar hierarquias de dimensão para fins de categorização ou classificação. Por exemplo, é possível definir uma hierarquia de categorização baseada em uma dimensão de elementos de custo e seus membros. Como alternativa, é possível definir uma hierarquia de classificação baseada em uma dimensão de objetos de custo e seus membros. As estruturas de relatório são usadas nas seguintes situações:
<ul>
<li>Você define alocações, taxas de custo e regras de acúmulo de custo.</li>
<li>Você exibe demonstrativos usando o espaço de trabalho.</li>
<li>Você define acesso para exibição de dados agregados.</li>
<li>Você exibe dados no Excel.</li>
</ul></td>
</tr>
<tr>
<td>Criar demonstrativos que podem ser exibidos no espaço de trabalho.</td>
<td>Use o espaço de trabalho para obter uma rápida visão geral dos custos reais e orçados, bem como dos desvios. É possível filtrar os dados por período ou nível de custo. O espaço de trabalho foi desenvolvido para os gerentes responsáveis pelo controle de custos. Ele adere às regras de acesso definidas para as hierarquias de dimensão.</td>
</tr>
<tr>
<td>Criar relatórios usando o Excel.
<blockquote>[!NOTE] Você deve executar o Microsoft Excel 2016.</blockquote>
</td>
<td>Você pode exportar dados de contabilização de custos diretamente para o Excel por meio das entidades de dados e usar a Microsoft PivotTable para criar relatórios.</td>
</tr>
</tbody>
</table>

## <a name="expense-management"></a>Gerenciamento de despesas

| O que você pode fazer | Por que isso é importante |
|-----------------|-----------------------|
| Reatribuir transações de cartão de crédito de funcionários demitidos. | Ocasionalmente, no momento em que um funcionário é demitido, sua conta de serviços de domínio do Active Directory (AD DS) é desabilitada quando são importadas as transações de cartão de crédito ativas que devem ser debitadas. Antes não era possível atribuir um delegado para entrada de despesas ou associar transações de cartão de crédito a um relatório de despesas. Agora é possível usar a página **Transações de cartão de crédito** para reatribuir o funcionário a qualquer transação de cartão de crédito na qual o funcionário associado foi demitido. Após a transação de cartão de crédito ser reatribuída, ela pode ser selecionada para um relatório de despesas e paga por meio do processo usual de reembolso. |
| Alterar informações de cartão de crédito de despesas para funcionários pendentes e anteriores. | É possível alterar as informações de cartão de crédito de gerenciamento para trabalhadores pendentes e anteriores. Antes era possível alterar as informações de cartão de crédito de despesas apenas se o trabalhador fosse um funcionário ativo. |
| Copiar um relatório de despesas. | Agora é possível copiar uma despesa existente ao criar despesas no mesmo relatório de despesas. Você pode copiar um relatório de despesas e todas as despesas associadas que não são de cartão de crédito em um novo relatório de despesas. Você ainda deve realizar qualquer discriminação necessária e associar os recibos exigidos, com base em categorias e políticas de despesas definidas. Você pode adicionar transações de cartão de crédito ao relatório de despesas optando por adicionar despesas não reconciliadas. |
| Editar despesas em massa. | Algumas transações de cartão de crédito pode não estar mapeadas em uma categoria de despesas ou podem ser mapeadas incorretamente quando importadas. Nesse caso, os funcionários devem alterar manualmente a categoria de despesas associada. Ao gerenciar as despesas não reconciliadas, agora você pode editar a categoria de despesas em massa quanto às despesas selecionadas. Além disso, ao gerenciar despesas selecionadas de um relatório de despesas específico, você pode editar o projeto e as informações adicionais em massa. |
| Alterar a taxa de câmbio para transações de cartão de crédito. | A taxa de câmbio real usada para uma transação de cartão de crédito pode diferir da taxa de câmbio definida no sistema. Antes não era possível aos funcionários alterar a taxa de câmbio de qualquer transação de cartão de crédito importada para o gerenciamento de despesas. Agora é possível definir o parâmetro na página **Parâmetros de gerenciamento de despesas** para permitir que a taxa de câmbio seja alterada para transações de cartão de crédito. |
| Definir atestado anticorrupção para despesas. | Alguns funcionários de uma empresa podem ter relações comerciais com representantes do governo, e algumas despesas que ocorrem como parte dessa relação podem ser percebidas como suborno. No gerenciamento de despesas, agora é possível definir um atestado anticorrupção que é mostrado nas categorias de despesas selecionadas, como jantares e presentes. Os funcionários devem selecionar se as despesas definidas no atestado anticorrupção atendem aos critérios estabelecidos pelas políticas de sua organização. |
| Evitar entrada manual de despesas para categorias de despesas específicas. | Uma categoria de despesas pode ser definida para representar uma transação de cartão de crédito na qual a categoria não pode ser alterada. Um exemplo é a taxa para pagamento atrasado do cartão de crédito. Agora você pode definir uma categoria de despesa que permite criar despesas apenas por meio de importação. Esse recurso impede que funcionários criem manualmente uma despesa para a categoria. Também impede que a categoria seja alterada quanto a transações que foram importadas e que usam essa categoria. |
| Associar um recibo a várias despesas. | Um recibo que é carregado para gerenciamento de despesas pode ser relacionado a várias despesas. Antes um recibo relacionado a várias despesas precisava ser carregado uma vez para cada despesa. Agora é possível associá-lo a uma despesa que já foi carregada e anexada a outra despesa no mesmo relatório de despesas. Além disso, ao carregar um recibo no cabeçalho do relatório de despesas, você pode selecionar uma ou mais linhas para anexar o recebido. |
| Criar despesas com datas futuras. | Ao copiar um relatório de despesas, por exemplo, a data da transação de uma despesa pode ser uma data futura. Versões anteriores não permitem despesas com datas futuras. Agora é possível criar e salvar despesas com data futura. No entanto, não é possível enviar uma despesa com data futura. |
| Configurar impostos de despesas de um estado/província. | Em alguns países/regiões, despesas incorridas em diferentes estados/províncias podem estar sujeitas a diferentes taxas de imposto sobre vendas. Agora é possível definir as configurações de imposto de despesas no nível do estado/província, não apenas no nível do país/região. Se o campo **Estado/província** na página **Configuração de imposto** for deixado em branco, o grupo de impostos será aplicado a todos os estados/províncias do país/região especificado. |
| Configurar tipos de cartão de crédito de despesas. | Antes não havia uma página na qual era possível criar tipos de cartão de crédito, como Visa, MasterCard ou AMEX, que poderiam ser usados com gerenciamento de despesas. Agora é possível criar tipos de cartão de crédito para usar com gerenciamento de despesas. A página está localizada na área **Configuração**, na seção **Cálculos e códigos**. |
| Definir um fluxo de trabalho de aprovação com vários níveis para relatórios de despesas. | Um novo fluxo de relatórios de despesas que permite um processo de aprovação com vários níveis. Os funcionários inserem os aprovadores interinos e os aprovadores finais ao criarem o relatório de despesas. Isso fará com que o fluxo de trabalho encaminhe o relatório de despesas ao aprovador interino primeiro. Após a provação do relatório de despesas nesse nível, o fluxo de trabalho vai encaminhá-lo ao aprovador final para aprovação final. |
| Criar e manter despesas não associadas a um relatório de despesas. | O usuário pode criar despesas e mantê-las (por exemplo, anexando ou discriminando os recibos ou atribuindo convidados) sem a necessidade de primeiro ter que criar um relatório de despesas. Uma ou mais despesas podem ser selecionadas e adicionadas a um novo relatório de despesas para que elas possam ser enviadas para aprovação. Uma nova página para manter despesas está disponível em **Gerenciamento de despesas** &gt; **Minhas despesas** &gt; **Despesas**. |

## <a name="financial-management"></a>Gerenciamento financeiro

<table>
<thead>
<tr>
<th>O que você pode fazer</th>
<th>Por que isso é importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>Rastrear estimativas de ativos fixos usando um único conceito de "registro".</td>
<td>Anteriormente, dois tipos separados de avaliação eram usados para rastrear valores de ativos fixos: modelos de valor e registros de depreciações. Na versão atual, esses dois conceitos foram combinados em um único conceito de avaliação chamado de “registros”. Registros apresentam toda a funcionalidade dos modelos de valor e registros de depreciações. Por exemplo, você pode desabilitar a opção de lançamento na contabilidade. Os registros lançados na contabilidade geralmente são usados para relatórios financeiros corporativos. Registros que não são lançados na contabilidade podem ser usados para relatórios de imposto.</td>
</tr>
<tr>
<td>Realizar o fechamento de exercício da contabilidade para várias entidades legais.</td>
<td>Para acelerar o processo de fechamento de exercício, agora é possível realizar esse fechamento para várias entidades legais em uma página de fechamento de exercício compartilhada. Grupos de entidades legais podem ser definidos, juntamente com configurações que devem ser retidas de um ano para o outro. Outros aprimoramentos de usabilidade também foram realizados no processo de fechamento de exercício.</td>
</tr>
<tr>
<td>Aproveitar as melhorias no reavaliação de moeda estrangeira da contabilidade.</td>
<td>Os seguintes melhoramentos foram feitos no processo da contabilidade para reavaliação de moeda estrangeira:
<ul>
<li>Um tipo de taxa de câmbio foi adicionado à conta principal. Esse tipo de taxa de câmbio agora é usado para determinar a taxa de câmbio durante a reavaliação de moeda. Se nenhum tipo de taxa de câmbio for definido, o processo continuará a usar o tipo de taxa de câmbio definido no razão.</li>
<li>Agora é mais fácil selecionar uma variedade de contas principais e moedas para o processo de reavaliação.</li>
<li>A reavaliação pode ser executada para várias entidades legais.</li>
<li>O sistema agora mantém um histórico de cada processo de reavaliação que foi executado, assim como do processo de reavaliação de contas a receber (AR) e contas a pagar (AP).</li>
<li>Ao realizar o processo, é possível visualizar os resultados da reavaliação. A visualização mostra os resultados de todas as entidades legais para as quais o processo foi executado. Depois, é possível lançar todas as entidades legais ou um subconjunto delas na visualização. Também é possível exportar os resultados na visualização para Excel.</li>
</ul></td>
</tr>
<tr>
<td>Exibir transações para mais níveis de lançamento.</td>
<td>Na página de lista <strong>Balancete</strong> e no relatório <strong>Demonstrativo de dimensão</strong>, agora é possível selecionar mais níveis de lançamento que foram adicionados à contabilidade. Ao selecionar os níveis de lançamento adicionais, os ajustes desses níveis são incluídos nos saldos na página de lista ou no relatório.</td>
</tr>
<tr>
<td>Anexar documentação explicativa ao modelo de fechamento do período financeiro.</td>
<td>Antes era possível anexar documentação após a conclusão de uma tarefa. Por exemplo, era possível anexar um relatório que foi gerado. Agora também é possível anexar documentação explicativa ao modelo. Essa documentação explicativa é copiada em cada tarefa na agenda de período financeiro de modo que o proprietário da tarefa possa exibir instruções sobre como concluí-la.</td>
</tr>
<tr>
<td>Definir a configuração da contabilidade intercompanhia em uma página compartilhada.</td>
<td>A <strong>Página de configuração de contabilidade intercompanhia</strong> agora é compartilhada para que a organização possa definir todos os pares de entidades legais que podem realizar transações entre si. Além disso, agora é possível inserir uma transação na entidade legal de origem, mas não da entidade legal de destino. Se a entidade legal puder iniciar uma transação intercompanhia, o par recíproco deve ser definido. Portanto, a entidade legal de destino também está configurada como entidade legal de origem.</td>
</tr>
<tr>
<td>Enviar documentos de justificativa para planos de orçamento.</td>
<td>Você pode criar um modelo de justificativa como documentação suplementar para qualquer valor de orçamento necessário. Os usuários podem preencher os detalhes do modelo e associar este ao plano de orçamento para ser usado durante o processo de aprovação.</td>
</tr>
<tr>
<td>Habilitar regras avançadas para entradas de registro de orçamento.</td>
<td>Se as regras avançadas forem configuradas na contabilidade, elas podem ser usadas em novas entradas e transferências no registro de orçamento.</td>
</tr>
<tr>
<td>Aproveitar a melhoria de visibilidade de atividade de faturamento de pagamento antecipado.</td>
<td>Uma nova página de lista <strong>Pagamentos antecipados em aberto</strong> fornece instantaneamente o status da atividade de faturamento de pagamento antecipado. A página fornece ao departamento de AP informações sobre ordens de compra com valores de pagamento antecipado remanescentes que devem ser faturados, valores faturados que devem ser pagos e valores de fatura pagos que devem ser aplicados a faturas padrão. Além disso, melhorias na aplicação automática de faturas de pagamentos antecipados pagas a faturas padrão ajudam o funcionário responsável pelo faturamento a realizar entrada de dados de forma mais eficiente.</td>
</tr>
<tr>
<td>Use o espaço de trabalho <strong>Faturamento de colaboração do fornecedor</strong>.</td>
<td>Um novo espaço de trabalho <strong>Faturamento</strong> na área <strong>Colaboração do fornecedor</strong> permite que fornecedores externos acessem suas próprias informações de fatura de forma segura. Por exemplo, fornecedores podem verificar se uma fatura foi paga ou enviar sua própria fatura. Essa alteração promove uma comunicação mais eficiente e oportuna com fornecedores externos. Portanto, o funcionário responsável pelo faturamento sofre menos interrupções.</td>
</tr>
<tr>
<td>Alternar entidades legais durante a entrada da fatura.</td>
<td>Os aprimoramentos permitem que os funcionários responsáveis pelo faturamento que devem inserir faturas de várias entidades legais mudem rapidamente a entidade legal nas páginas de faturamento. Esse recurso possibilita a esses funcionários economizar tempo, já que eles não precisam mais se desconectar da entidade legal e se conectar a uma outra. Com as páginas <strong>Diário de faturas globais</strong> e <strong>Faturas de fornecedor</strong>, os usuários podem alterar a entidade legal durante a entrada dos dados.</td>
</tr>
<tr>
<td>Suporte para arquivos eletrônicos para o programa de transmissão federal/estadual combinado 1099 da administração fiscal</td>
<td>Quando a chave de configuração <strong>US</strong> é habilitada, o processo de transmissão eletrônica 1099 possibilita uma funcionalidade adicional que está em conformidade com as regulamentações da administração fiscal do programa de transmissão federal/estadual combinado. A administração fiscal estabeleceu esse programa para que ele pudesse enviar eletronicamente retornos de informações para estados participantes.</td>
</tr>
<tr>
<td>Melhorias de liquidação</td>
<td>As melhorias ajudam os responsáveis por pagamentos a fazer liquidações de forma mais eficiente, já que eles podem permitir que vários pagamentos não lançados sejam liquidados em relação à mesma fatura.</td>
</tr>
<tr>
<td>Exibição interempresarial</td>
<td>Responsáveis por pagamentos centralizados agora podem exibir faturas vencidas nas empresas. Os espaços de trabalho <strong>Pagamentos de fornecedores</strong> e <strong>Pagamentos de cliente</strong> agora fornecem melhor visibilidade e controle das faturas vencidas possibilitando uma forma de exibir e filtrar em todas as empresas que fazem parte de uma hierarquia organizacional de pagamento centralizada.</td>
</tr>
<tr>
<td>Usar o espaço de trabalho <strong>Gerenciamento bancário</strong>.</td>
<td>Um novo espaço de trabalho <strong>Gerenciamento bancário</strong> ajuda a rastrear contas bancárias e saldos de suas entidades legais. São imediatamente disponibilizados saldos atuais e pendentes de todas as contas, e você pode regressar dos saldos a comprovantes de transação detalhados. Você também pode verificar os dados de saldo histórico de cada conta bancária ou um resumo de todas as contas bancárias da companhia, em exibições de curto e longo prazo. Você pode ter uma melhor ideia da reconciliação de conta bancária, porque a data da última reconciliação de cada conta bancária é reportada, além de haver um indicador de reconciliações em progresso.</td>
</tr>
<tr>
<td>Importar extratos bancários eletrônicos de todas as entidades legais em uma única etapa.</td>
<td>Você pode importar extratos bancários eletrônicos de todas as entidades legais em uma única etapa. Os arquivos de extrato bancário contêm demonstrativos de muitas contas bancárias e entidades legais, os arquivos ZIP podem conter vários arquivos de extrato bancário. Usando um único processo de importação, você pode iniciar a reconciliação de todas as contas bancárias reportadas em todas as entidades legais. Esse recurso ajuda a economizar tempo, pois você não precisa alternar entre empresas e várias importações de demonstrativo. Você também pode executar automaticamente regras de correspondência em relação a todos os demonstrativos em cada empresa.</td>
</tr>
<tr>
<td>Acompanhamento de avaliação</td>
<td>Um único ativo fixo pode ter várias avaliações para diferentes padrões de conta, bem como lançar opcionalmente as transações associadas na contabilidade. Antes essas avaliações eram acompanhadas por meio de modelos de valores ou registros de depreciações. Agora é possível acompanhar essas avaliações, conhecidas atualmente como registros, por meio de um conjunto comum de diários, consultas e relatórios. A experiência unificada simplifica a implementação e reduz o número de interfaces de que os processos periódicos precisam.</td>
</tr>
<tr>
<td>Aproveitar os aprimoramentos das execuções de depreciação entre empresas.</td>
<td>Agora você pode iniciar uma execução de depreciação de ativos em todas as entidades legais em uma única página. Você também pode lançar automaticamente os diários após eles serem criados. Você pode enviar a criação e o lançamento dos diários para processamento em lote para que a depreciação seja executada em segundo plano. Esses aprimoramentos reduzem ineficiências, pois você não precisa iniciar execuções de depreciação individuais separadamente para cada empresa. O aprimoramento também permite melhor gerenciamento centralizado dos ativos fixos.</td>
</tr>
</tbody>
</table>

## <a name="human-capital-management"></a>Gerenciamento de capital humano

<table>
<thead>
<tr>
<th>O que você pode fazer</th>
<th>Por que isso é importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>Criar um diário de desempenho.</td>
<td>Após a conclusão da sua revisão, você geralmente reúne informações sobre atividades ou eventos que contribuíram para o seu sucesso como funcionário durante o período de revisão. Você pode adicionar uma entrada ao diário de desempenho para documentar essas atividades e eventos. Você também pode associar esses eventos e atividades a uma meta ou uma previsão de desempenho para fornecer mais informações ao revisor.</td>
</tr>
<tr>
<td>Criar metas mais detalhadas.</td>
<td>Você tem mais controle sobre o conteúdo das metas que você define. Você pode criar medidas para as metas, vincular entradas de diário de desempenho às medidas e anexar e exibir documentos. Você pode armazenar metas como modelos e reutilizá-las para rápida configuração.</td>
</tr>
<tr>
<td>Criar revisões de desempenho mais detalhadas.</td>
<td>Previsões de desempenho, conhecidas formalmente como discussões, agora são flexíveis o bastante para permitirem feedback contínuo e revisões mais formais. Você pode obter metas ativas e lançar comentários sobre elas, bem como adicionar seções em uma revisão das suas competências. São fornecidas mais seções, nas quais você pode adicionar ou exibir medidas, entradas de diários de desempenho, anexos e aprovações relacionados à revisão.</td>
</tr>
<tr>
<td>Associar hierarquias de posições adicionais a fluxos de trabalho.</td>
<td>Você pode associar um fluxo de trabalho a uma hierarquia de posições. Você também pode modificar as etapas de fluxo de trabalho para otimizar o processo de aprovação de modo que este se adeque às suas necessidades comerciais. Portanto, você pode definir uma estrutura de aprovação efetiva de acordo com as várias relações de relatório que sua organização usa.</td>
</tr>
<tr>
<td>Suporte de fluxo de trabalho para inserir números de identificação pessoal (PINs) no autoatendimento para funcionários.</td>
<td>O recurso de fluxo de trabalho de RH foi expandido e agora inclui suporte para PINs. Os funcionários podem adicionar e editar o PIN para aumentar a eficiência. Entretanto, os funcionários do RH podem revisar essas informações para verificar a precisão e a integridade antes de adicioná-las ao registro de funcionários.</td>
</tr>
<tr>
<td>Criar modelos de metas e usá-los para adicionar novas metas.</td>
<td>Você pode criar modelos de metas para metas compartilhadas por muitos funcionários na empresa. Os funcionários podem adicionar suas próprias metas a partir de um modelo, gerentes podem adicionar metas para a equipe a partir de um modelo e os membros de equipe de RH podem adicionar metas para funcionários de toda a empresa.</td>
</tr>
<tr>
<td>Criar grupos de metas e usá-los para adicionar novas metas.</td>
<td>Você pode adicionar modelos de meta a um grupo e usar o grupo para criar uma ou mais metas para um funcionário, uma equipe, uma posição, um departamento ou a empresa.</td>
</tr>
<tr>
<td>Ter mais controle sobre o processo de revisão.</td>
<td>Você pode usar um fluxo de trabalho para controlar o processo de revisão. Você pode criar modelos de revisão e usá-los para criar revisões. Você também pode adicionar classificações a uma revisão.</td>
</tr>
<tr>
<td>Usar períodos de revisão para definir o prazo para a revisão.</td>
<td>Você pode definir um período para avaliação de desempenho, com as datas inicial e final da revisão sendo inseridas automaticamente. Entretanto, você pode alterar essas datas padrão quando necessário.</td>
</tr>
<tr>
<td>Acesse cinco novos pacotes de conteúdo do Power BI para Recursos Humanos</td>
<td>Os novos pacotes de de conteúdo permitem que organizações de recursos humanos e gerentes de recursos humanos analisem o seguinte:
<p>Métricas de força de trabalho</p>
<ul>
<li>Divisões demográficas por idade, sexo e estado civil</li>
<li>Comparar as taxas de atrito ano a ano e ver uma lista de razões que os funcionários deram para deixar a organização</li>
<li>Ver uma lista de posições abertas, bem como uma comparação de posições abertas a fechadas</li>
</ul>
<p>Remuneração e benefícios</p>
<ul>
<li>Comparar empregados por hora e assalariados</li>
<li>Ver o número de empregados inscritos nos benefícios disponíveis</li>
<li>Visualizar empregados por tipo de emprego</li>
</ul>
<p>Recrutamento</p>
<ul>
<li>Analisar os candidatos com base no número de candidatos, de onde estão vindo, e para quais as posições eles estão se candidatando</li>
</ul>
<p>Treinamento organizacional</p>
<ul>
<li>Registro em curso por localidade</li>
<li>Participação em cursos por status</li>
<li>Lista de funcionários registrados para cursos</li>
</ul>
<p>Competências e desenvolvimento de funcionários</p>
<ul>
<li>Lista de competências por funcionário</li>
<li>Divisão dos tipos de habilidade por membro da equipe</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="localizations"></a>Localizações

<table>
<thead>
<tr>
<th>O que você pode fazer</th>
<th>Por que isso é importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>As localizações estão disponíveis para 18 países adicionais:
<ul>
<li>Áustria</li>
<li>Bélgica</li>
<li>Brasil</li>
<li>China</li>
<li>República Tcheca</li>
<li>Estônia</li>
<li>Finlândia</li>
<li>Hungria</li>
<li>Itália</li>
<li>Letônia</li>
<li>Lituânia</li>
<li>Noruega</li>
<li>Polônia</li>
<li>Arábia Saudita</li>
<li>Espanha</li>
<li>Suécia</li>
<li>Suíça</li>
<li>Tailândia</li>
</ul>
<p>Os seguintes países também precisam da localização varejo. A localização do Retail para esses países não foi concluída e está planejada somente para H1 CY2017:</p>
<ul>
<li>Brasil</li>
<li>República Tcheca</li>
<li>Estônia</li>
<li>Hungria</li>
<li>Letônia</li>
<li>Lituânia</li>
<li>Malásia</li>
<li>Polônia</li>
<li>Suécia</li>
</ul>
</td>
<td>O Dynamics 365 for Operations está disponível em mais 18 países. Como parte do nosso esforço para tornar a localização mais fácil e configurável, recursos de relatórios eletrônicos e regulatórios foram convertidos em configurações de relatório eletrônico (ER), enquanto alguns relatórios do Microsoft SQL Server Reporting Services (SSRS) foram convertidos em configurações de ER que usam modelos do Excel. Esses recursos convertidos são mencionados especificamente depois nesta tabela.</td>
</tr>
<tr>
<td>Japão – Agrupar ativos fixos ao imprimir o formulário 26 e suas tabelas acrescentadas.</td>
<td>O formulário 26 deve ser enviado a cada cidade na qual a empresa opera. Para evitar mais trabalho ao imprimir o formulário 26, ativos fixos podem ser automaticamente agrupados e classificados por local.</td>
</tr>
<tr>
<td>Japão – Consultar os valores de depreciação acelerada e adicional no perfil.</td>
<td>O perfil pode fornecer uma estimativa precisa dos valores de depreciação acelerada e adicional.</td>
</tr>
<tr>
<td>Japão – Calcular progressivamente o imposto retido na fonte.</td>
<td>O governo japonês exige que você calcule imposto retido na fonte progressivamente, com base no valor do pagamento.</td>
</tr>
<tr>
<td>Japão – Importar o arquivo do código postal de grandes edifícios empresariais.</td>
<td>A arquivo do código postal que a autoridade fornece para grandes edifícios empresariais pode ser importado para o sistema. Com isso, o endereço pode ser derivado dos códigos postais.</td>
</tr>
<tr>
<td>Japão – Configurar um período ocioso para ativos fixos.</td>
<td>Os períodos ociosos permitem que o usuário pause a depreciação de ativos fixos durante um período especificado. Essa funcionalidade é exigida pela regulamentação.</td>
</tr>
<tr>
<td>Europa – Configurar um número de registro de imposto sobre valor agregado (IVA) para o endereço de um participante usando a estrutura de ID de registro.</td>
<td>É possível configurar um número de registro de IVA para o endereço de um participante usando a estrutura de ID de registro e uma nova categoria de registro de <strong>ID de IVA</strong>.</td>
</tr>
<tr>
<td>Finlândia – Configurar um número de cliente de alfândega para o endereço de um participante usando a estrutura da ID de registro.</td>
<td>É possível configurar um número de cliente de alfândega para o endereço de um participante usando a estrutura da ID de registro and e a nova categoria de <strong>ID de cliente alfandegário</strong>.</td>
</tr>
<tr>
<td>França – Imprimir fatura de cliente em um layout que seja específico da França.</td>
<td>A impressão de faturas de cliente é ajustada para atender a requisitos específicos franceses.</td>
</tr>
<tr>
<td>França – Aplicar numeração cronológica de documentos por período fiscal.</td>
<td>Para atender aos requisitos específicos da França para número de faturas do cliente, é possível configurar sequências de números para faturas do cliente por período fiscal.</td>
</tr>
<tr>
<td>Localização da Áustria – Configurações de ER</td>
<td>
<ul>
<li>Formato XML austríaco da lista de vendas da UE</li>
<li>Formato da Intrastat da Áustria</li>
<li>Formato de pagamento de transferência de crédito ISO20022 da Áustria</li>
<li>Formato de pagamento de débito direto ISO20022 da Áustria</li>
<li>Formato EDIFACT-PAYMUL austríaco</li>
<li>Declaração de IVA da Áustria</li>
</ul>
</td>
</tr>
<tr>
<td>Localização da Bélgica – Configurações de ER</td>
<td>
<ul>
<li>Formato BLWI da Bélgica</li>
<li>Formato XML da lista de vendas da UE da Bélgica</li>
<li>Relatório de ativos fixos da Bélgica</li>
<li>Formato de Intervat da Bélgica</li>
<li>Formato da Intrastat da Bélgica</li>
<li>Relatório de total de vendas da fatura da Bélgica</li>
<li>Formato de exportação da transação do razão da Bélgica</li>
<li>Formato de pagamento SWIFT da Bélgica</li>
<li>Formato de importação do demonstrativo bancário CODA da Bélgica</li>
<li>Formato de pagamento de transferência de crédito ISO20022 da Bélgica</li>
<li>Formato de pagamento de débito direto ISO20022 da Bélgica</li>
</ul>
</td>
</tr>
<tr>
<td>Localização do Brasil – Configurações de ER</td>
<td>
<ul>
<li>GIA SP para o Brasil</li>
<li>GIA-ST para o Brasil</li>
</ul>
</td>
</tr>
<tr>
<td>Localização da República Tcheca – Configurações de ER</td>
<td>
<ul>
<li>Formato XML da lista de vendas da UE da República Tcheca</li>
<li>Formato da Intrastat da República Tcheca</li>
<li>Declaração de IVA da República Tcheca</li>
</ul>
</td>
</tr>
<tr>
<td>Localização da China – Configurações de ER</td>
<td>
<ul>
<li>Formato de relatório de classificação por vencimento de clientes da China</li>
<li>Formato do relatório de análise de valor devido de clientes da China</li>
<li>Formato de Relatório de classificação por vencimento de fornecedores para China</li>
<li>Formato do relatório de análise de valor devido de fornecedores da China</li>
<li>Formato de análise de classificação por vencimento de pagamentos a receber da China</li>
<li>Formato de relatório de saldo de clientes da China</li>
<li>Formato do relatório de saldo da conta contábil da China</li>
<li>Formato do relatório de saldo de fornecedores da China</li>
<li>Arquivo GBT da China</li>
<li>Formato para arquivo de exportação de imposto dourado</li>
<li>Formato de relatório de variação do consumo da China</li>
</ul>
</td>
</tr>
<tr>
<td>Localização da Estônia – Configurações de ER</td>
<td>
<ul>
<li>Formato XML da lista de vendas da UE da Estônia</li>
<li>Formato da Intrastat da Estônia</li>
<li>Demonstrativo da reclassificação de estoque da Estônia</li>
<li>Formato de pagamento de transferência de crédito ISO20022 da Estônia</li>
<li>Relatório de aviso de saldo do cliente da Estônia</li>
<li>Declaração de IVA da Estônia</li>
</ul>
</td>
</tr>
<tr>
<td>Localização da Finlândia – Configurações de ER</td>
<td>
<ul>
<li>Formato TXT da lista de vendas da UE da Finlândia</li>
<li>Formato da Intrastat da Finlândia</li>
<li>Formato de pagamento de transferência de crédito ISO20022 da Finlândia</li>
</ul>
</td>
</tr>
<tr>
<td>Localização da Hungria – Configurações de ER</td>
<td>
<ul>
<li>Formato XML da lista de vendas da UE da Hungria</li>
<li>Formato da Intrastat da Hungria</li>
<li>Formato simplificado da Intrastat da Hungria</li>
<li>Formato de exportação da lista de fatura da Hungria</li>
<li>Declaração de IVA da Hungria</li>
<li>Declaração discriminada de IVA da Hungria</li>
<li>Demonstrativo de estoque da Hungria</li>
<li>Formato de pagamento MultiCash da Hungria</li>
</ul>
</td>
</tr>
<tr>
<td>Localização da Itália – Configurações de ER</td>
<td>
<ul>
<li>Formato da Intrastat da Itália</li>
<li>Formato de fatura de projeto da Itália</li>
<li>Formato de fatura de vendas da Itália</li>
<li>Formato de pagamento de transferência de crédito ISO20022 da Itália</li>
<li>Formato de pagamento de débito direto ISO20022 da Itália</li>
<li>Formato de remessa de coleção RIBA da Itália</li>
<li>Relatório de transações de imposto doméstico da Itália</li>
<li>Relatório de lista de bloqueios da Itália</li>
<li>Relatório Modello770 da Itália</li>
<li>Relatório de comunicação de imposto anual da Itália</li>
</ul>
</td>
</tr>
<tr>
<td>Localização da Letônia – Configurações de ER</td>
<td>
<ul>
<li>Relatório de uso de recebimento de pagamento à vista (LV)</li>
<li>Formato XML de lista de vendas da Letônia</li>
<li>Formato XML de correções de lista de vendas da Letônia</li>
<li>Formato (A) da Intrastat da Letônia</li>
<li>Formato (B) da Intrastat da Letônia</li>
<li>Lista de contagem de estoque da Letônia</li>
<li>Demonstrativo de contagem de estoque da Letônia</li>
<li>Movimento do estoque da Letônia</li>
<li>Nota de entrega de transferência interna da Letônia</li>
<li>Documento de reclassificação de estoque da Letônia</li>
<li>Formato de pagamento de transferência de crédito ISO20022 da Letônia</li>
<li>Declaração de IVA da Letônia</li>
</ul>
</td>
</tr>
<tr>
<td>Localização da Lituânia – Configurações de ER</td>
<td>
<ul>
<li>Formato XML da lista de vendas da UE da Lituânia</li>
<li>Formato da Intrastat da Lituânia</li>
<li>Demonstrativo de estoque da Lituânia</li>
<li>Formato de pagamento de transferência de crédito ISO20022 da Lituânia</li>
<li>Relatório de reconciliação entre cliente e fornecedor da Lituânia</li>
<li>Declaração de IVA da Lituânia</li>
</ul>
</td>
</tr>
<tr>
<td>Localização da Noruega – Configurações de ER</td>
<td>
<ul>
<li>Formato de carta de cobrança da Noruega</li>
<li>Formato de pagamento AutoGiro da Noruega</li>
<li>Formato de pagamento de cliente AvtaleGiro da Noruega</li>
<li>Formato de pagamento de cliente eFaktura da Noruega</li>
<li>Formato de pagamento de transferência de crédito ISO20022 da Noruega</li>
<li>Formato de pagamento NETS da Noruega</li>
</ul>
</td>
</tr>
<tr>
<td>Localização da Polônia – Configurações de ER</td>
<td>
<ul>
<li>Formato da Intrastat da Polônia</li>
<li>Documentos de depósito da Polônia</li>
<li>Documento de reclassificação de estoque da Polônia</li>
<li>Formato de pagamento MultiCash da Polônia</li>
<li>Formato de pagamento estrangeiro MultiCash da Polônia</li>
<li>Relatório de confirmação de saldo do cliente da Polônia</li>
</ul>
</td>
</tr>
<tr>
<td>Localização da Arábia Saudita – Configurações de ER</td>
<td>Formato de alocação de encargo de várias LCs bancárias da Arábia Saudita</td>
</tr>
<tr>
<td>Localização da Espanha – Configurações de ER</td>
<td>
<ul>
<li>Formato TXT de lista de vendas da Espanha</li>
<li>Formato da Intrastat da Espanha</li>
<li>Formato de fatura de projeto da Espanha</li>
<li>Formato de fatura de vendas da Espanha</li>
<li>Formato de pagamento de transferência de crédito ISO20022 da Espanha</li>
<li>Formato de pagamento de débito direto ISO20022 da Espanha</li>
<li>Formato do livro de registro de IVA espanhol</li>
<li>Formato do resumo de registro de IVA espanhol</li>
<li>Exportação de declaração 347 para ASCII da Espanha</li>
<li>Relatório de declaração 347 da Espanha</li>
</ul>
</td>
</tr>
<tr>
<td>Localização da Suécia – Configurações de ER</td>
<td>
<ul>
<li>Formato da Intrastat da Suécia</li>
<li>Formato de pagamento de cliente Bankgirot Autogiro da Suécia</li>
<li>Formato de pagamento de fornecedor Bankgirot da Suécia</li>
<li>Formato de pagamento SWIFT da Suécia</li>
<li>Formato de exportação SIE da Suécia</li>
<li>Formato de pagamento de transferência de crédito ISO20022 da Suécia</li>
</ul>
</td>
</tr>
<tr>
<td>Localização da Suíça – Configurações de ER</td>
<td>
<ul>
<li>Formato de pagamento DebitDirect da Suíça</li>
<li>Formato de pagamento de débito direto LSV da Suíça</li>
<li>Formato de pagamento de transferência de crédito ISO20022 da Suíça</li>
<li>Formato de pagamento de débito direto ISO20022 da Suíça</li>
<li>Formato de importação do demonstrativo bancário ESR da Suíça</li>
</ul>
</td>
</tr>
<tr>
<td>Alemanha – Formato de pagamentos do fornecedor de exportação em DTAZV</td>
<td>A Alemanha requer DTAZV com especificação de formato estrangeiro, que representa uma mensagem de transferência de crédito (pagamento do fornecedor) de acordo com a especificação de pagamentos internacionais da Alemanha para uma conta em um banco estrangeiro ou em um banco doméstico em uma moeda estrangeira.</td>
</tr>
</tbody>
</table>

### <a name="electronic-reporting"></a>Relatório eletrônico

| O que você pode fazer | Por que isso é importante |
|-----------------|-----------------------|
| Configurar relatórios de ER para inserir dados, em vários formatos, de armazenamento de gerenciamento de documentos para mensagens eletrônicas geradas. | Os relatórios de ER inserem dados nas mensagens eletrônicas que são geradas no armazenamento de gerenciamento de documentos. Portanto, os anexos de um documento comercial podem ser adicionados às mensagens eletrônicas geradas para esse documento, de acordo com os requisitos legais. Atualmente, esses anexos podem ser adicionados no formato MIME para uma mensagem XML que foi gerada. Como alternativa, os anexos podem ser adicionados no formato Base64 a uma mensagem binária gerada. |
| Configurar relatórios de ER para gerar documentos eletrônicos em formato Excel, Microsoft Word ou PDF. | Uma configuração habilita relatórios de ER a gerar documentos eletrônicos em três diferentes formatos: planilha OpenXML (Excel), Word e formato de dados de formulários XML (XFDF) (PDF). Os usuários podem selecionar um formato adicionando um modelo de formato a uma relatório de ER como documento do Excel, Word ou em PDF. |
| Configurar relatórios de ER para inserir dados nos cabeçalhos e rodapés de documentos eletrônicos de uma página gerados no formato de uma planilha OpenXML, além de controlar quebras de página. | Relatórios de ER podem inserir dados comerciais nos cabeçalhos e rodapés de uma página, bem como controlar onde ocorrem quebras de página. Sendo assim, os relatórios podem permitir seções estáticas nas partes superior e inferior dos documentos eletrônicos que são gerados. Também podem permitir paginação específica desses documentos para estarem em conformidade com os requisitos legais. |
| Configurar o destino dos relatórios de ER para que a saída seja enviada como email e para que os dados comerciais e a lógica de ER (expressões) possam ser usados para especificar, no momento da execução, o endereço de email a ser usado. | Anteriormente, ao configurar um destino de ER, era possível definir o endereço de email do destinatário de saída no momento da criação. Agora é possível configurar uma expressão no formato de ER. Essa expressão pode ser selecionada em um destino como a origem do endereço de email de cada configuração de formato e componente de saída (pasta ou arquivo) separadamente. Portanto, durante a execução de um relatório de ER, cada arquivo gerado pode ser enviado para um destinatário diferente, e o endereço de email pode ser definido com base na lógica e nos dados comerciais de ER. |
| Configurar o destino dos relatórios de ER para que a saída seja enviada para a pasta do Microsoft SharePoint como um novo arquivo nomeado ou uma nova versão do arquivo existente e para que os dados comerciais possam ser usados na estrutura do Microsoft Power BI como um conjunto de dados ou um relatório. | Atualmente, ao configurar relatórios de ER, é possível preparar facilmente (sem codificação) os dados comerciais solicitados para que possam ser usados pela estrutura do Power BI. Ao executar esses relatórios de ER, é possível fornecer à estrutura do Power BI os dados comerciais apropriados e/ou relatórios do Excel que já estão disponíveis. Ao programar as execuções de relatório de modo recorrente, você pode estabelecer o envio agendado de dados comerciais do Dynamics 365 for Operations para o Power BI para permitir o agendamento de atualização dos relatórios baseados no Power BI. |
| Configurar relatórios de ER para usar a parte do documento eletrônico que já foi gerado como uma fonte de dados para gerar o restante desse documento. | Você pode configurar relatórios de ER que criam a saída no formato de texto para fazer a contagem de linhas do documento. Depois, as informações podem ser usadas em outras partes do documento para criar linhas incluindo detalhes de resumo. As informações de resumo (totais e números) podem ser computadas e impressas nos documentos eletrônicos gerados, sem a necessidade de transformações adicionais dos dados. Portanto, esse recurso melhora o desempenho da execução do relatório e permite que a manutenção futura do formato de ER configurado continue mais fácil. |
| Configurar relatórios de ER para especificar a extensão de nome de arquivo dos documentos eletrônicos gerados no formato do texto. | Você pode configurar relatórios de ER para criar a saída em formato de texto para que ela possa ser salva como um arquivo com uma extensão específica. Além da extensão .txt padrão, é possível configurar extensões como .csv e .prn, de acordo com a especificação de formato. |
| Criar relatórios de ER baseados em uma versão específica de um modelo de ER. | Anteriormente, durante a criação de um formato de ER, só era possível usar a versão mais recente do modelo de ER selecionado como local de origem dos dados do formato. Agora é possível selecionar qualquer versão disponível do modelo de ER selecionado. Esse recurso permite que você mantenha relatórios de ER do ano atual e crie paralelamente uma versão do modelo de ER do próximo ano. |
| Pesquisar fontes de dados e formatos/modelos por texto ou artefato selecionado com apenas um clique. Resolver proativamente conflitos de rebase e conflitos entre configurações. Configurar relatórios de ER para criar várias mensagens de validação para erros descobertos até a execução de relatório ser interrompida. | Várias melhorias na experiência de usuário (UX) na estrutura de ER ajudam os usuários a trabalhar com ER de forma mais eficiente e fácil. |
| Mostrar o espaço de trabalho **ER** em relatórios do Power BI. | Os usuários podem configurar a página **Espaço de trabalho ER** para que ela inclua novos itens de menu e blocos dinâmicos que executem relatórios baseados no Power BI. |

## <a name="payroll"></a>Folha de Pagamento

<table>
<thead>
<tr>
<th>O que você pode fazer</th>
<th>Por que isso é importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>Configurar registros de pagamento e processar folhas de pagamento usando uma funcionalidade que seja equivalente àquela do módulo <strong>Folha de pagamento</strong> no Microsoft Dynamics AX 2012 R3.</td>
<td>Agora você pode configurar e processar folhas de pagamento dos EUA usando um recurso definido que é equivalente ao do AX 2012 R3.
<ul>
<li>Você pode configurar ciclos e períodos de pagamento, ciclos e períodos de trabalho, códigos de ganhos e grupos de códigos de ganhos, agendas, tipos de licença e planos de acúmulo de benefícios.</li>
<li>Você também pode configurar deduções obrigatórias para os benefícios e impostos, bem como registrar as informações de folha de pagamento em relação a cargos e funcionários para fins de relatório e análise.</li>
<li>Você também pode configurar e gerenciar deduções para consignações e arrecadações de imposto e para todas as taxas administrativas associadas.</li>
</ul>
</td>
</tr>
<tr>
<td>Monitorar e processar seu processo de período de pagamento usando o novo espaço de trabalho <strong>Gerenciamento de folha de pagamento</strong>.</td>
<td>Agora é possível monitorar com facilidade seu processamento de folha de pagamento. Administradores de folha de pagamento podem verificar rapidamente demonstrativos de ganhos e pagamentos que precisem de atenção para que a execução do pagamento seja completa e precisa. O espaço de trabalho <strong>Gerenciamento de folha de pagamento</strong> permite que os usuários monitorem e executem processo completos de um único espaço de trabalho.</td>
</tr>
<tr>
<td>Gerar arquivos de pagamento positivo para verificações de folha de pagamento.</td>
<td>Há uma nova extensão para a funcionalidade de pagamento positivo de gerenciamento de caixa e bancos para pagamentos da folha de pagamento. Itens de menu separados foram adicionados por meio do processo principal para permitir configuração isolada específica para folha de pagamento. A funcionalidade é idêntica ao recurso de pagamento positivo principal que foi liberado no aplicativo do Microsoft Dynamics AX versão 7.0.1 (maio de 2016). Por causa dessa extensão, os dados de folha de pagamento são totalmente isolados do resto das suas transações de pagamento positivo. Tal isolamento ajuda a garantir que somente usuários de folha de pagamento possam acessar e verificar os dados relacionados à folha de pagamento.</td>
</tr>
<tr>
<td>Importar linhas de demonstrativo de ganhos de uma fonte externa utilizando a nova entidade de dados de linhas do demonstrativo de ganhos.</td>
<td>Uma nova e importante entidade de dados possibilita integração com sistemas externos de cálculo de ganhos e tempo. A entidade de dados importa linhas de demonstrativo de ganhos e executa a mesma lógica padrão que o usuário inseriu diretamente na declaração de ganhos. Após a importação, as linhas são automaticamente associadas ao documento de declaração de ganhos apropriado. Se um documento de declaração de ganhos adequado não existir, um documento é criado automaticamente.</td>
</tr>
</tbody>
</table>

## <a name="planning-and-scheduling"></a>Planejamento e agendamento

| O que você pode fazer | Por que isso é importante |
|-----------------|-----------------------|
| Definir configurações padrão de ordem de venda e compra, com base em qualquer dimensão do produto ativo no produto mestre. Portanto, você pode definir configurações padrão de ordem para a unidade de manutenção de estoque (SKU) ou uma SKU parcial. | Você pode especificar configurações de ordem padrão que se aplicam a uma dimensão do produto ou uma combinação de dimensões de produto ativas.<p>**Exemplo**</p><p>Você vende um produto que é chamado de "camiseta polo". Esse produto está disponível em duas cores: verde e azul. Também está disponível em dois tamanhos: pequeno e médio. Cor e tamanho são dimensões de produto ativas para camiseta polo. É possível bloquear compras de todas as camisetas polo verdes, independentemente do tamanho.</p> |

## <a name="product-master-data"></a>Dados de produto mestre

<table>
<thead>
<tr>
<th>O que você pode fazer</th>
<th>Por que isso é importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>Definir todas as configurações de ordem padrão e configurações de ordem específicas para sites ao mesmo tempo, de uma única página.</td>
<td>Esse recurso fornece uma melhor visão geral das configurações de item.</td>
</tr>
<tr>
<td>Criar uma nomenclatura para números de grade de produto.</td>
<td>Você pode incluir elementos, como atributos, caracteres e dimensões de produto, nos números da sua grade de produto. Ao criar uma ordem de venda ou compra, você pode encontrar rapidamente a grade de produto específica.</td>
</tr>
<tr>
<td>Procurar produtos e grades de produtos em cenários de venda e compra.</td>
<td>Ao criar uma linha de venda ou compra, você pode procurar produtos usando as dimensões e qualquer número do produto, com exceção dos GTINs (números globais de item comercial) e códigos de barra. Trata-se de uma pesquisa de texto completo que substitui a pesquisa "Começa com" existente que é usada na lista de busca de venda e compra. Esse recurso permite que você encontre grupos de produtos com propriedades similares ou um único produto com características exclusivas. Para ativar esse recurso, selecione o parâmetro <strong>Habilitar pesquisa para pesquisa de produtos</strong> na página <strong>Parâmetros de pesquisa</strong>.</td>
</tr>
<tr>
<td>Especificar a grade de produto diretamente ao criar uma transação de venda ou compra. Como alternativa, você pode selecionar em uma lista de combinação de dimensões válida.</td>
<td>Esse recurso é uma melhoria de produtividade.
<p><strong>Exemplo </strong></p>
<p>Você vende um produto que é chamado de "camiseta polo". Esse produto está disponível em duas cores: verde e azul. Também está disponível em dois tamanhos: pequeno e médio. Cor e tamanho são dimensões de produto ativas para camiseta polo. Quando você insere uma linha de venda para camiseta polo de cor verde e tamanho pequeno, não é preciso inserir dados nos campos <strong>Número de item</strong>, <strong>Cor</strong> e <strong>Tamanho</strong>. Você pode criar a linha seguindo uma das seguintes etapas:</p>
<ul>
<li>No campo <strong>Número de item</strong>, insira o número de grade de produto, o valor de uma cor ou o tamanho. Na busca, localize a grade específica que deseja vender e crie a linha de venda.</li>
<li>No campo <strong>Número de item</strong>, insira o número do item. Acesse qualquer campo de dimensão de produto. Na pesquisa <strong>Dimensão do produto</strong>, você verá todas as combinações de dimensão lançadas que se aplicam à camiseta polo. Em uma etapa, é possível selecionar a grade de produto que deseja vender.</li>
</ul>
</td>
</tr>
<tr>
<td>Especificar se os números do produto aparecem ou não nas páginas transacionais.</td>
<td>As páginas transacionais, como ordens de venda e compra, mostram apenas os campos <strong>Número de item</strong> e <strong>Nome do produto</strong>. Para ver o campo <strong>Número do produto</strong>, selecione o parâmetro <strong>Mostrar números do produto em formulários</strong> em <strong>Parâmetros de gerenciamento de informações do produto</strong>.</td>
</tr>
</tbody>
</table>

## <a name="project-management-and-accounting"></a>Gerenciamento e contabilidade de projeto

| O que você pode fazer | Por que isso é importante |
|-----------------|-----------------------|
| Usar seleção tardia ao lançar propostas de fatura em um lote. | Os contadores de projeto podem configurar um trabalho em lotes para selecionar automaticamente propostas para lançamento, se essas propostas atenderem ao critérios que são especificados no trabalho em lotes. Esse recurso melhora a automação do lançamento de faturas, já que o trabalho em lotes pode ser executado continuamente, e seleciona propostas para lançamento de forma automática. |
| Criar análises na área de trabalho do Power BI. | O conteúdo de Business Intelligence (BI) para dados relacionados a projetos e recursos pode ser facilmente criado na área de trabalho do Power BI. |
| Usar pagamentos antecipados de ordens de compra e incluí-los no processo de estimativa de projeto. | Para ordens de compra de projeto, os pagamentos antecipados devem ser processados antes que algum pagamento possa ser liberado para fornecedores. Essas faturas de pagamento antecipado agora aparecem no processo de estimativa/reconhecimento de projeto para projetos do tipo **Preço fixo**. |
| Acessar e gerenciar estimativas de custo e receita e requisitos de item, diretamente de uma tarefa de estrutura de detalhamento de trabalho (WBS). | É possível gerenciar estimativas de custo, estimativas de receita e requisitos de item de uma tarefa de WBS específica na caixa de diálogo dos detalhes dessa tarefa na exibição de planejamento da WBS. |
| Selecionar uma fonte de financiamento em diários de taxa. | Se o contrato para um projeto contiver várias fontes de financiamento, é possível selecionar uma fonte de financiamento específica quando as taxas forem lançadas. Se você não selecionar uma fonte de financiamento, as regras de financiamento que são especificadas no contrato serão usadas para alocar a taxa. |
| Abrir demonstrativos de projeto no Excel. | As novas entidades de dados para atualizações do razão e de orçamento permitem abrir dados de demonstrativos do projeto no Excel e criar análises usando a funcionalidade do Excel. |
| Usar apenas uma chave de configuração para habilitar a funcionalidade para gerenciamento e contabilidade de projeto (PMA). | As chaves de configuração relacionadas ao projeto foram substituídas por uma chave de configuração de projeto que ativa a funcionalidade de PMA. |

## <a name="retail-and-commerce"></a>Varejo e comércio

### <a name="advanced-warehouse-management-in-a-retail-store"></a>Gerenciamento de depósito avançado em uma loja de varejo

Os varejistas podem usar a solução de gerenciamento de depósito avançado (WHS) nas suas lojas e realizar as atualizações necessárias para que os recursos de ponto de venda (PDV) sejam compatíveis com ela. Os processos da solução portátil devem funcionar em uma loja, pois eles funcionam em qualquer depósito. Todos os processos atuais de inventário de loja do Retail e quaisquer processos de PDV que criam ou atualizam transações de estoque são atualizados para que possam usar os requisitos específicos de depósitos habilitados para WHS.

| O que você pode fazer | Por que isso é importante |
|-----------------|-----------------------|
| Usar o PDV para procurar estoque disponível nas lojas habilitadas para WHS. | Ao procurar um estoque, o processo deve funcionar da mesma forma que antes. A procura deve mostrar as quantidades disponíveis no nível do depósito e não devem considerar o local, status do estoque ou dimensões de placa de licença. |
| Usar o PDV para processar um recibo de produto para uma ordem de transferência em uma loja habilitada para WHS. | Você pode receber ordens de transferência no PDV para lojas e itens habilitados para WHS. O usuário deve ser capaz de selecionar os locais para recebimento, bem como inserir as IDs de placa de licença para preencher automaticamente as linhas de recebimento. |
| Usar o PDV para processar um recibo de produto para uma ordem de compra em uma loja habilitada para WHS. | Você pode receber ordens de compra no PDV para lojas e itens habilitados para WHS. O usuário deve ser capaz de selecionar os locais para recebimento, bem como inserir as IDs de placa de licença para preencher automaticamente as linhas de recebimento. |
| Usar o PDV para processar uma remessa de produtos de uma loja habilitada para WHS. | Você pode registrar transferências do PDV para lojas e itens habilitados para WHS. O usuário deve ser capaz de selecionar os locais para remessa, o status do estoque deve ser gerado automaticamente e as placas de licença devem ser ignoradas. |

### <a name="enable-seamless-omni-channel-commerce"></a>Habilitar comércio de canal omni completo

Comércio de canal omni completo refere-se a gerenciamento e processamento de ordens em lojas tradicionais, lojas online, call centers e experiências de comércio móvel. Em relação a essa versão, os seguintes investimentos foram realizados na área:

- Melhorias de publicação para lojas de comércio eletrônico
- Um novo aplicativo para dispositivo móvel voltado ao consumidor que permite descoberta de produtos, gerenciamento de contas e venda online.

| O que você pode fazer | Por que isso é importante |
|-----------------|-----------------------|
| Consumidor: a versão atual do aplicativo para dispositivo móvel voltado ao consumidor permite que os recursos (pesquisa de produto e procura por categoria) adicionem ao carrinho e finalizem compras como convidado. Os varejistas também podem aplicar as marcas das suas empresas ao aplicativo e depois disponibilizá-lo nas lojas de aplicativos do Android e iOS. | Os varejistas podem criar facilmente aplicativos voltados para o consumidor que permitem ao cliente procurar produtos e remetê-los como convidado em seus dispositivos móveis. |
| Listas de desejo do cliente para lojas online de comércio colaborativo | Os fornecedores de software independentes (ISVs) podem usar o controle de listas de desejo para permitir que os usuários criem e gerenciem várias listas na sua loja online, além de exibir/usar essas listas no PDV. |
| Criação assíncrona de cliente por meio de lojas online de comércio eletrônico | Os ISVs agora podem criar contas de clientes mesmo quando o Commerce Data Exchange: Real-time Service não está indisponível. |
| Publicar produtos de canal do Retail Server para lojas de terceiros. | Atualmente, o Retail Server é compatível com a autenticação de serviço a serviço. Os ISVs podem aproveitar a publicação de produtos do canal do Retail Server para lojas de terceiros. |

### <a name="extensibility"></a>Extensibilidade

- Agora os projetos de tempo de execução de comércio são lacrados no SDK do Retail.
- Implantação e atendimento mais fáceis por meio de pacotes de componentes da Microsoft e pacotes de ISV componentizados para o PDV, Retail Server, bancos de dados e estações de Hardware.

| O que você pode fazer | Por que isso é importante |
|-----------------|-----------------------|
| CRT/Retail Server: varejistas ou ISVs podem estender o CRT por meio de ganchos de extensão. Alterações de códigos embutidos não são mais compatíveis. | Para habilitar a integração e implantação contínuas, as alterações de códigos embutidos devem ser completamente evitadas. Além disso, para permitir uma rápida tomada de hotfix sem combinação de códigos e implantação de componentes de CRT. |

### <a name="personalized-product-recommendations"></a>Recomendações de produtos personalizados

| O que você pode fazer | Por que isso é importante |
|-----------------|-----------------------|
| Visualize recomendações personalizadas de produtos em vários pontos de contato no ponto de venda (PDV) para determinar o que um cliente pode estar interessado, com base em seu histórico de compras, itens na lista de desejos e itens que outros clientes compraram online e em lojas físicas. | Para os varejistas com grandes catálogos, recomendações personalizadas ajudam o cliente com a descoberta de produtos e capacitam os associados da loja com clientela inteligente. Ao exibir produtos voltados aos interesses e hábitos de compra de determinado público, as recomendações do produto podem ajudar os varejistas com a venda adicional e podem aumentar a retenção de cliente. No Retail, as recomendações do produto são habilitadas pelos serviços cognitivos e aprendizado de máquina do Microsoft Azure. |

### <a name="pos-task-recorder"></a>Gravador de tarefas do PDV

| O que você pode fazer | Por que isso é importante |
|-----------------|-----------------------|
| Varejistas podem usar um gravador de tarefas de PDV para produzir materiais, diagramas de modelador de processo de negócios (BPM) e gerar conteúdo de ajuda para melhorar a produtividade e realizar melhores análises e design de aplicativos. | Para habilitar a integração e implantação contínuas, as alterações em linha devem ser completamente evitadas. Além disso, para permitir uma rápida tomada de hotfix sem combinação de códigos e implantação de componentes de CRT. |
| Ajuda em tempo real no PDV. | O caixa/gerente pode obter ajuda em tempo real no PDV sobre processos comerciais sem mudar de contexto. |

### <a name="store-system-providing-a-seamless-on-premises-store-experience"></a>Sistema de armazenamento: fornecimento contínuo de experiência de armazenamento local

O sistema de armazenamento é uma opção de implantação para varejistas que ajuda a controlar um conjunto de operações de armazenamento, no armazenamento local, na nuvem pública da Microsoft ou na própria nuvem privada do cliente. Para esta versão, o escopo é somente no armazenamento. Para oferecer um suporte melhor a ambientes com conectividade de rede lenta ou não confiável, devemos fornecer uma opção que permita aos varejistas implantar o banco de dados do canal e o Retail Server na loja. Com isso, eles podem continuar a executar os principais cenários comerciais mesmo quando não há conectividade com matrizes. Com base nos vários pontos de dados, que incluíram discussões entre a equipe de engenharia, resultados de pesquisa com cliente e análise da concorrência, identificamos o seguinte escopo de solução como o ajuste ideal para nossos clientes-alvo:

- Um pacote de autoatendimento está disponível para o sistema de armazenamento.
- A instalação padrão é uma implantação integrada, mas a implantação personalizada é permitida.
- Habilitar fácil implantação/autoatendimento.
- O Retail Server e o banco de dados da loja estão na loja, juntamente com o serviço Async Client.
- O Retail Server na loja comunica-se diretamente com o Application Object Server (AOS) na matriz para o sistema de armazenamento.
- Suportar vários cenários entre terminais quando não há conectividade com a matriz.
- O Retail Modern POS e o Cloud POS sempre se comunicam com o Retail Server na loja.
- Dar suporte ao Retail Modern POS e o Cloud POS quando não houver conectividade com a matriz.
- Dar suporte a um banco de dados offline específico do Retail Modern POS (isolado para cada instância do Retail Modern POS) quando não houver conectividade com a matriz.
- A autenticação é baseada apenas em serviço a serviço para o sistema de armazenamento.
- As chamadas de serviços em tempo real não são suportadas se não houver conectividade com a Internet.
- A conectividade de banco de dados direta do Retail Modern POS com o banco de dados do canal não é suportada.
- Habilitar telemetria/monitoramento.

| O que você pode fazer | Por que isso é importante |
|-----------------|-----------------------|
| Um varejista baixa o instalador do serviço de autoatendimento do sistema de armazenamento da página do banco de dados do canal na matriz do Dynamics AX e depois o arquivo de configuração. | O varejista pode baixar facilmente o pacote de autoatendimento. |
| Uma varejista instala o sistema de armazenamento usando o instalador de autoatendimento. | O varejista pode instalar o sistema de armazenamento usando o pacote de autoatendimento. |
| O gerente de TI configura o sistema de armazenamento no Dynamics 365 for Operations (banco de dados do canal, perfil do canal, armazenamento e pacote implantável). | O gerente de TI pode configurar o armazenamento de forma fácil e eficiente. |
| O varejista opera o Retail Modern POS no armazenamento local e pode realizar operações em tempo real, como emissão de vale presente, quando há conectividade. | O varejista pode realizar ações em tempo real no sistema de armazenamento quando há conectividade. |
| O varejista pode sincronizar os dados no sistema de armazenamento local com a matriz sempre que houver conectividade. | O varejista pode sincronizar com e no sistema de armazenamento quando há conectividade. |
| O varejista pode ter comunicação segura entre o sistema de armazenamento local e a matriz. | O varejista pode se comunicar de forma segura a partir do sistema de armazenamento quando há conectividade. |
| O gerente de TI e o Microsoft Operations podem monitorar e fazer relatórios sobre o sistema de armazenamento local (diagnósticos e alterações de relatórios). | O gerente de TI e o Microsoft Operations podem monitorar o sistema de armazenamento e solucionar problemas de forma eficiente. |

### <a name="universal-windows-platform-app-for-retail-modern-pos"></a>Aplicativo da plataforma universal do Windows do Retail Modern POS

Atualmente, o Retail Modern POS está disponível apenas como um aplicativo do Windows 8.1 para computadores desktop e tablets e como Cloud POS para navegadores de desktop ou tablet. Nessa versão, o Retail Moderns POS está sendo convertido para o aplicativo do Plataforma Universal do Windows. Essa alteração permitirá que o Retail Modern POS seja executado em qualquer dispositivo do Windows 10 (desktop, tablet ou telefone) e até mesmo alterne entre exibições de dispositivos habilitado para Continuum.

| O que você pode fazer | Por que isso é importante |
|-----------------|-----------------------|
| Habilitar uma importante funcionalidade de PDV para dispositivos de pequeno formato. | A funcionalidade do Retail POS está disponível para telefones e outros dispositivos de pequeno formato que executam o Windows 10. |

## <a name="supply-chain-management"></a>Gerenciamento da cadeia de fornecedores

### <a name="consignment-inventory"></a>Estoque em consignação

| O que você pode fazer | Por que isso é importante |
|-----------------|-----------------------|
| Como fornecedor, é possível armazenar matérias-primas no depósito do cliente. Como cliente, é possível adiar a compra real até que a matéria-prima seja necessária para produção. | Manter um estoque de matérias-primas pode envolver custos consideráveis. Usando estoque em consignação, um fornecedor pode armazenar matérias-primas no depósito do cliente. Depois, o cliente pode adiar a compra real até que a matéria-prima seja necessária para produção. As matérias-primas são ordenadas e recebidas por meio de uma ordem de reabastecimento de consignação. A ordem de reabastecimento registra transações físicas, mas não afeta a contabilidade. Para distinguir entre itens de estoque de propriedade do cliente e itens de estoque de propriedade do fornecedor, é possível usar a dimensão de estoque Proprietário. A alteração de propriedade de estoque é feita por um processo do diário que controla a transferência de propriedade para matérias-primas do estoque de propriedade do fornecedor para o estoque de propriedade do cliente. Esse processo aciona a criação de uma ordem de venda e um recibo de produto.<blockquote>[!NOTE] Esse recurso está limitado a uma consignação de entrada das matérias-primas para produção. Não está integrado com o gerenciamento de depósito (WHS) e o gerenciamento de transporte (TMS).</blockquote> |
| Como fornecedor, obter informações sobre a quantidade de estoque em consignação que é transferido para o cliente. | Para cobrar um cliente, o fornecedor precisa de informações sobre as matérias-primas que foram compradas do estoque em consignação e sobre a data da compra. O fornecedor também pode monitorar o estoque disponível no site do cliente usando a interface de colaboração de fornecedor. |
| Mover o estoque de propriedade do fornecedor usando um diário de transferência. | Para rastrear a posição física do estoque de propriedade do fornecedor, você deve ser capaz de registrar a posição no sistema. Usando um diário de transferência, você pode registrar a movimentação física do estoque, como a movimentação de um local em um depósito para outro local nesse depósito. |
| Ajustar o estoque de propriedade do fornecedor usando o diário de contagem. | É importante que você mantenha o estoque de sistema disponível em sincronia com o estoque físico real. O estoque de propriedade do fornecedor pode ser ajustado interna e externamente por meio de processos de contagem, como ajuste de quantidade e processos de diário de contagem. |
| Saiba mais sobre o suporte de consignação no Dynamics 365 for Operations | Para obter mais informações sobre o suporte para processos de consignação, consulte [Consignação](../../../supply-chain/inventory/consignment.md), [Configurando consignação](../../../supply-chain/inventory/set-up-consignment.md), [Criar uma ordem de reabastecimento de consignação (guia de tarefas)](../../../supply-chain/inventory/tasks/create-consignment-replenishment-order.md) e [Alterar a propriedade de estoque de remessa com base na demanda de produção (guia de tarefas)](../../../supply-chain/inventory/tasks/change-ownership-consignment.md). |

### <a name="vendor-collaboration-previously-known-as-the-vendor-portal"></a>Colaboração do fornecedor (antes conhecida como o portal do fornecedor)

| O que você pode fazer | Por que isso é importante |
|-----------------|-----------------------|
| Habilitar fornecedores para responder a cada linha de ordem de compra e sugerir alterações. | Em alguns casos, os fornecedores desejam aceitar algumas linhas de ordem de compra, mas rejeitar outras. Agora os fornecedores podem gerenciar individualmente linhas de ordem de compra. Cada linha pode ser rejeitada, aceita ou aceita com alterações. Por exemplo, os fornecedores podem alterar a data de entrega, dividir a entrega e a quantidade ou sugerir um item alternativo. |
| Habilitar fornecedores para gerenciar informações pessoais de contato. | Os fornecedores podem manter informações pessoais de contato da sua empresa. Essas informações incluem nomes, endereços de email e números de telefone. O acesso a esse recurso é concedido por meio de uma função de segurança exclusiva. |
| Compartilhar documentos que estão relacionados a ordens de compra com fornecedores. | Quando é preciso compartilhar um documento com um fornecedor, como um documento sobre requisitos, é conveniente vincular o documento à ordem de compra relevante. O fornecedor pode então compartilhar observações e anexos com o cliente vinculando o documento à resposta deste para a ordem de compra. O gerenciamento de documentos é a estrutura de suporte subjacente, e somente observações e anexos que são classificados como "externos" podem ser compartilhados com fornecedores. |
| Provisionar novos usuários fornecedores. | Se seus fornecedores usarem a interface de colaboração de fornecedor, eles terão um meio perfeito de solicitar novas contas de usuários quando os novos contatos precisarem de acesso para colaboração de fornecedor. Os profissionais de compras podem enviar uma solicitação para uma conta de usuário de uma pessoa de contato na organização do fornecedor. Uma pessoa de contato do fornecedor que já é um usuário da colaboração de fornecedor também pode enviar esse tipo de solicitação. Por fim, essa solicitação criará um usuário no Dynamics 365 for Operations com funções de segurança específicas para fornecedores. Isso também facilita uma solicitação para o portal B2B do Microsoft Azure provisionar o usuário com uma nova conta de usuário do Azure Active Directory (Azure AD). Os fornecedores também podem solicitar que as contas do usuário fornecedor sejam desativadas ou que as funções de segurança sejam modificadas. |
| Saiba mais sobre suporte para colaboração de fornecedor no Dynamics 365 for Operations. | Para obter mais informações sobre colaboração de fornecedor, consulte [Colaboração de fornecedores com fornecedores externos](../../../supply-chain/procurement/vendor-collaboration-work-external-vendors.md), [Colaboração do fornecedor com clientes](../../../supply-chain/procurement/vendor-collaboration-work-customers-dynamics-365-operations.md), [Gerenciar usuários de colaboração do fornecedor](../../../supply-chain/procurement/manage-vendor-collaboration-users.md), [Configurar e manter colaboração de fornecedor](../../../supply-chain/procurement/set-up-maintain-vendor-collaboration.md) e [Espaço de trabalho de faturamento de colaboração do fornecedor](../../../finance/accounts-payable/vendor-portal-invoicing-workspace.md). |

### <a name="intercompany-order-processing"></a>Processamento de ordens intercompanhia

<table>
<thead>
<tr>
<th>O que você pode fazer</th>
<th>Por que isso é importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>Definir, diretamente nas linhas de ordem de venda, de onde e como a demanda deve se originar.
<p><strong>Exemplo </strong></p>
<p>Criar uma linha de ordem de venda e especificar a entrega direta como o tipo de entrega. O fornecedor primário é adicionado à linha de ordem de venda como o ponto de fornecimento.</p>
</td>
<td>O fluxo para tomada de ordem foi significativamente melhorado. Agora você pode definir, diretamente nas linhas de ordem de venda, de onde e como a demanda deve se originar. Você não precisará mais esperar até que todas as linhas tenham sido adicionadas à ordem de venda. As novas opções nas linhas de ordem de venda permitem que você especifique o tipo de entrega ao especificar o fornecedor. Quando você associa um fornecedor a linhas de ordem de venda, cadeias de ordem são criadas para entrega do fornecedor.
<ul>
<li>O fornecedor pode ser um fornecedor intercompanhia que usa uma ordem de compra interna e uma ordem de venda ou pode ser um fornecedor externo que usa uma ordem de venda externa.</li>
<li>O tipo de entrega pode ser <strong>Entrega direta</strong> ou <strong>Estoque</strong>. O tipo de entrega <strong>Estoque</strong> indica que o fornecedor deve fornecer ao estoque local antes de enviar ao cliente.</li>
</ul>
</td>
</tr>
<tr>
<td>Criar uma promessa de ordem diretamente das linhas de ordem de venda.
<p><strong>Exemplo </strong></p>
<p>Criar uma linha de ordem de venda originária de um fornecedor intercompanhia. Deixar a linha. As datas de entrega são calculadas de acordo com a disponibilidade na empresa de fornecimento.</p>
</td>
<td>Ao criar linhas de ordem de venda que usam as novas informações de fornecimento, as datas de entrega são calculadas de acordo com o controle <strong>Data de entrega</strong>. Por exemplo, se um fornecedor intercompanhia for selecionado, a disponibilidade na empresa de fornecimento será calculada. Assim, as cadeias de ordem são criadas automaticamente juntamente com linhas de ordem de venda. Essa funcionalidade ajuda a garantir que as datas de entrega se tornem visíveis na empresa de fornecimento para que os perfis disponíveis para promessa (ATP) possam lidar com demandas antecipadas diretamente quando as ordens de venda são criadas.</td>
</tr>
<tr>
<td>Revisar a disponibilidade do produto em todos os locais de fornecimento e selecionar a melhor opção de fornecimento.</td>
<td>A página <strong>Alternativas de entrega</strong> foi remodelada e agora fornece informações valiosas sobre todos os fornecedores internos e externos. Essas informações incluem opções de fornecimento para compras de fornecedor. Quando você seleciona um modo de entrega, o sistema calcula as datas de entrega viáveis. Você pode selecionar facilmente a melhor opção para o cliente e aplicá-la a cada linha de ordem de venda.</td>
</tr>
</tbody>
</table>

### <a name="warehouse-enhancements-for-high-volume-distribution-centers"></a>Melhorias de depósito para centros de distribuição de alto volume

| O que você pode fazer | Por que isso é importante |
|-----------------|-----------------------|
| Criar trabalho após as mercadorias terem sido embaladas em uma estação de embalagem. | Esse recurso é útil quando há processos adicionais após o trabalho manual de embalagem (como paletização, inspeção de qualidade, consolidação de remessas ou alterações em docas de carga). O novo tipo de trabalho **Separação de contêineres embalados** permite que você modele essas tarefas usando linhas de trabalho separadas. Agora é possível modelar estações de embalagem para gerar trabalho após embalagem. Esse trabalho pode ser usado para organizar o movimento do estoque embalado. |
| Agrupar contêineres na estação de embalagem. | Esse recurso permite que vários pacotes sejam agrupados em um contêiner ou placa de licença na estação de embalagem. Por exemplo, um operador de comércio eletrônico/atacado pode agrupar 100 pacotes individualmente em um único contêiner (como um palete ou uma caixa). Depois, esse contêiner pode ser movido, preparado ou carregado por meio de uma única instrução de trabalho que um trabalhador gera digitalizando um único código de barras (placa de licença) para o contêiner agrupado. Esse recurso minimiza as transações de trabalho para mover vários contêineres empacotados menores. Para obter mais informações, consulte [Criar um item de menu de dispositivo móvel para consolidação de matrícula (guia de tarefas)](../../../supply-chain/warehousing/tasks/create-mobile-device-license-plate-consolidation.md). |
| Criar uma política de versão para contêineres empacotados. | O trabalho acionado por uma versão de contêiner pode ser criado de forma automática ou manual. Quando é automática, o trabalho é gerado em fechamento de contêiner usando a diretiva de local e estrutura de modelo de trabalho. Quando a versão é manual, o empacotador pode decidir se o trabalho deve ou não ser gerado para um único contêiner ou para um grupo de contêineres. Esse recurso reduz o risco de que contêineres sejam selecionados e movidos antes de serem movidos da estação de embalagem. Também permite versões agrupadas não guiadas por sistema. |
| Realocação de separação insuficiente | O suporte foi adicionado para processos de separação insuficiente para ajudar os associados que não conseguem selecionar mercadorias e desejam realizar a ordem quando o item necessário estiver disponível em outro local. É possível usar um processo de realocação automática que usa as diretivas de localização para recuperar as mercadorias se elas estiverem disponíveis em outras localizações. Como alternativa, quando a realocação manual é usada, o dispositivo móvel mostra uma lista de locais juntamente com a quantidade disponível. O trabalhador do depósito pode então selecionar em que local usar o estoque. Esses dois métodos podem ser definidos individualmente ou em combinação como um único comando no menu do trabalhador de depósito. Quando uma realocação manual é usada, o trabalhador de depósito pode selecionar uma quantidade de itens de separação insuficiente de vários locais. Para obter mais informações, consulte [Configurar realocação de item de pouca seleção (guia de tarefas)](../../../supply-chain/warehousing/tasks/set-up-short-picking-item-reallocation.md). |
| Mover o estoque com trabalho a ele associado. | É possível mover o estoque com trabalho a ele associado. Esse recurso pode ser útil se, por exemplo, um trabalhador desejar limpar determinado espaço de doca de entrada e mover paletes registrados que precisam ser levados para outro local de entrada. A doca é esvaziada e pode receber carga adicional de mercadoria, e o estoque que foi movido é atualizado com novas informações de armazenamento. Esse recurso também pode ser usado para liberar espaço nos locais de separação movendo o estoque com trabalho a ele associado e criando espaço para reabastecimento. Você também pode usá-lo para mover cargas de um local de preparo para outro sem perder o trabalho de carregamento que foi gerado. Assim, o recurso pode ajudar a otimizar o tempo necessário para carregar caminhões quando eles chegam. Você pode mover o estoque que foi reservado para ordens de venda, transferência de problemas de ordem, transferência de recibos de ordem e ordens de compra. A movimentação não é permitida se ela fizer com que as linhas se dividam. Por exemplo, se você tiver uma linha de trabalho para 100 peças de um item, não será possível movimentar apenas 30 peças desse item para outro local. |
| Combinar placas de licença com trabalho a elas associado. | Você pode combinar placas de licença com trabalho de saída a elas associado. Por exemplo, quando uma separação foi dividida em várias peças de trabalho, pode ser útil permitir que as placas de licença sejam combinadas após serem entregues no local de preparo. As placas de licença só podem ser consolidadas se estiverem no mesmo local, forem membros da mesma carga e tiverem as mesmas informações de remessa. |
| Congelar o trabalho de separação associado ao reabastecimento no nível de linha. | Agora é possível congelar um trabalho no nível de linha em vez do nível de cabeçalho para que os funcionários possam realizar as linhas de separação que não foram congeladas por reabastecimento de demanda. Portanto, um atacadista com grandes ordens de venda ou um varejista com grandes ordens de venda ou ordens de transferência de reabastecimento podem permitir que o trabalho de separação seja iniciado em todas as linhas que não estão sujeitas ao trabalho de reabastecimento. Com isso, o trabalho de separação e reabastecimento pode ser concluído paralelamente. Esse recurso pode ser configurado para que você possa optar por congelar ou não no nível de cabeçalho ou no nível de linha. Você também pode usar ambos os métodos e criar um modelo para cada método. A configuração de cabeçalho/linha é definida nos modelos de trabalho, mas é possível alterá-la no trabalho gerado. |
| Cancelar o trabalho usando o dispositivo móvel. | Agora é possível cancelar o trabalho usando o dispositivo móvel, com ou sem reabastecimento de demanda. Antes era preciso usar o cliente avançado. Para habilitar essa funcionalidade, crie um item de menu de dispositivo móvel com o modo definido como **Indireto** e o código de atividade definido como **Cancelar trabalho**. |

### <a name="warehouse-operation-enhancements"></a>Aprimoramentos na operação de depósito

| O que você pode fazer | Por que isso é importante |
|-----------------|-----------------------|
| Modelar tipos diferentes de contêiner. | Você pode usar tipos diferentes de contêiner no depósito para otimizar o armazenamento e por outras razões. A nova entidade Tipo de contêiner apresenta as características físicas dos tipos de contêiner. Agora é possível associar placas de licença com um tipo de contêiner específico e usar limites de estoque de local. Por exemplo, você pode usar esse recurso para controlar quantos paletes (ou outros tipos de contêiner) você permite em um local específico. Os tipos de contêiner já foram adicionados aos grupos de sequências de unidade para adição de tipos de contêiner para o processo de recebimento. Os tipos de contêiner podem ser usados com diretivas de local de entrada e saída. Eles também podem ser usados na exibição de estoque disponível para ajudar a determinar quantos tipos de contêiner estão atualmente armazenados e à disposição. Para obter mais informações, consulte a postagem de blog [Uso das placas de licença associado com um tipo de contêiner para orientar processos de gerenciamento de depósito](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/06/20/use-of-license-plates-associated-with-a-container-type-to-drive-warehouse-management-processes/). Embora essa postagem de blog descreva uma atualização para o Microsoft Dynamics AX 2012, o mesmo suporte foi adicionado agora ao Dynamics 365 for Operations. |
| Reverter remessas. | Em um depósito, você deve ser capaz de lidar com alterações tardias. Por exemplo, algumas mercadorias talvez estejam danificadas, razão pela qual você não pode enviá-las. Como alternativa, uma cliente pode fazer uma solicitação atrasada de cancelamento ou alteração de uma ordem. O Dynamics 365 for Operations agora permite reverter uma remessa. Portanto, é possível cancelar uma guia de remessa e atualizá-la com as quantidades corretas posteriormente. De forma semelhante, no fluxo de entrada, é possível cancelar recibos de produtos para que uma versão atualizada possa ser criada. |
| Usar paletes com itens mistos. | Agora é possível receber e registrar um palete "misto". Um palete misto consiste em diferentes itens que são montados em um palete para uma ou várias linhas ou ordens de compra. Todos os registros podem ser resumidos em uma placa de licença de destino. Esse processo é habilitado por meio do dispositivo móvel do depósito. Por exemplo, quando o palete de itens mistos chega ao depósito, o responsável pelo recebimento identifica os itens e as quantidades no palete antes de este ser movido para um local de armazenamento exclusivo. Os locais de armazenamento são identificados por modelos de trabalho e diretivas de local. Se os locais de armazenamento forem disseminados para vários itens com locais fixos, esse recurso criará tantas linhas de trabalho de armazenamento quantos itens diferentes existirem no palete misto. Esse recurso torna o registro e o armazenamento dos paletes de itens mistos recebidos mais rápidos e flexíveis. Para obter mais informações, consulte a postagem de blog [Receber e registrar um palete com linhas do documento de origem misto usando uma placa](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/13/receive-and-register-a-pallet-with-mixed-source-document-lines-using-1-license-plate-purchase-order-matching/) e as informações sobre suporte para palete misto no [anúncio de nossa recente atualização cumulativa](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/06/30/whats-new-in-cu11-for-wms-and-tms/). Embora essa postagem de blog descreva uma atualização para o AX 2012, o mesmo suporte foi adicionado agora ao Dynamics 365 for Operations. |

### <a name="minor-feature-enhancements-in-supply-chain-management"></a>Melhorias de recurso menores no gerenciamento da cadeia de suprimentos

<table>
<thead>
<tr>
<th>O que você pode fazer</th>
<th>Por que isso é importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>Usar novas entidades de dados para importar e exportar dados.</td>
<td>Você pode importar e exportar dados usando essas entidades de dados:
<ul>
<li>Fratura de frete</li>
<li>Agregação disponível por depósito e status de estoque</li>
<li>Encargos de estoque</li>
<li>Cotação</li>
</ul>
</td>
</tr>
<tr>
<td>Usar o controle de Gantt aprimorado para desenvolver cenários interativos de planejamento.</td>
<td>O controle de Gantt aprimorado permite que você desenvolva novos cenários interativos de planejamento e entregue APIs aperfeiçoadas que podem ser usadas para personalizar a aparência de atividades. Estas são algumas das novas APIs:
<ul>
<li>Arrastar e soltar atividades verticalmente</li>
<li>Adicionar/remover atividades</li>
<li>Visualizar períodos registrados em barra de resumo</li>
<li>Alterar cor e estilo de fronteiras de atividade</li>
<li>Alterar cor, estilo e plano de fundo de texto em grade</li>
</ul>
</td>
</tr>
<tr>
<td>Controlar melhor o planejamento de materiais e recursos.</td>
<td>Algumas melhorias foram feitas no planejamento de materiais e recursos:
<ul>
<li>A margem de emissão agora é controlado quando um item está disponível.</li>
<li>Substituir a data de entrega ao confirmar ordens planejadas.</li>
<li>Priorizar o cumprimento de ordens no estoque de segurança.</li>
<li>Evitar a programação de ordens planejadas no passado.</li>
</ul>
</td>
</tr>
<tr>
<td>Relatar o consumo real da produção e exibir o status do estoque.</td>
<td>É possível exibir o consumo real da produção. Além disso, uma nova caixa de seleção <strong>Exibir status do estoque</strong> adicionada a <strong>Movimento</strong> no item de menu <strong>Criação de trabalho</strong> permite exibir o status do estoque.</td>
</tr>
<tr>
<td>Calcular o peso volumétrico, se as taxas da transportadora forem baseadas no peso volumétrico.</td>
<td>Um novo mecanismo de taxa do TMS baseado no peso volumétrico foi adicionada para que você possa calcular o peso volumétrico.</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Recursos adicionais

[Home page de Novidades ou alterações no Finance and Operations](whats-new-changed.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
