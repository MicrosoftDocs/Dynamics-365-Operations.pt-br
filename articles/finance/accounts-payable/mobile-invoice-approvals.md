---
title: Aprovações de fatura móvel
description: Este tópico tem como objetivo fornecer uma abordagem prática para criar cenários móveis tirando aprovações da fatura de fornecedor do celular como um caso de uso.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 88ba96b1d9d2f722528a4a920eabe4ab64304a7a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440304"
---
# <a name="mobile-invoice-approvals"></a>Aprovações de fatura móvel

[!include [banner](../includes/banner.md)]

Os recursos móveis permitem que um usuário corporativo crie experiências móveis. Para cenários avançados, a plataforma também permite que os desenvolvedores estendam as funcionalidades que desejam. A maneira mais eficaz de aprender alguns dos novos conceitos em dispositivo móvel é passar pelo processo de desenvolvimento de alguns cenários. Este tópico tem como objetivo fornecer uma abordagem prática para criar cenários móveis tirando aprovações da fatura de fornecedor do celular como um caso de uso. Esse tópico deve ajudá-lo a criar outras variações de cenários e também pode ser aplicado a outros cenários que não são relacionados a faturas de fornecedor.

<a name="prerequisites"></a>Pré-requisitos
-------------

| Pré-requisito                                                                                            | descrição                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Pré-leitura do manual móvel                                                                                |[Plataforma móvel](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)                                                                                                  |
| Dynamics 365 Finance                                                                              | Um ambiente com a versão 1611 e a Platform update 3 (novembro de 2016)                   |
| Instalar hotfix KB 3204341.                                                                              | O gravador de tarefas pode registrar erroneamente dois comandos Fechar para caixas de diálogo suspensas; isso está incluído na Platform update 3 (atualização de novembro de 2016). |
| Instalar hotfix KB 3207800.                                                                              | Este hotfix habilita a exibição de anexos no cliente móvel; isso está incluído na Platform update 3 (atualização de novembro de 2016).           |
| Instalar hotfix KB 3208224.                                                                              | Código do aplicativo para o aplicativo móvel de aprovação de fatura de fornecedor; isso está incluído na versão 7.0.1 (maio de 2016).                          |
| Um dispositivo Android, iOS ou Windows que tenha o aplicativo móvel instalado. | Procurar pelo aplicativo na loja de aplicativo apropriada.                                                                                                                     |

## <a name="introduction"></a>Apresentação
Aprovações móveis para faturas de fornecedor exigem os três hotfixes mencionados na seção "Pré-requisitos". Esses hotfixes não fornecem um espaço de trabalho para as aprovações de fatura. Para saber o que é um espaço de trabalho no contexto de dispositivo móvel, leia o manual do dispositivo mencionado na seção “Pré-requisitos”. O espaço de trabalho das aprovações de fatura deve ser criado. 

Cada organização orquestra e define seu processo comercial para faturas de fornecedor de forma diferente. Antes de criar uma experiência móvel para aprovações da fatura de fornecedor, considere os seguintes aspectos do processo comercial. A ideia é usar esses pontos de dados o máximo possível para otimizar a experiência de usuário no dispositivo.

-   Quais campos do cabeçalho de fatura o usuário desejará ver na experiência móvel, e em que ordem?
-   Quais campos das linhas de fatura o usuário desejará ver na experiência móvel, e em que ordem?
-   Quantas linhas de fatura estão presentes em uma fatura? Aplicar a regra 80-20 aqui e otimizá-la para 80%.
-   Os usuários desejarão consultar as distribuições contábeis (codificação de fatura) no dispositivo móvel durante as revisões? Se a resposta a essa pergunta for sim, considere as seguintes perguntas:
    -   Quantas distribuições contábeis (preço bruto, impostos, encargos, separações, e assim por diante) existem para uma linha de fatura? Novamente, aplique a regra 80-20.
    -   As faturas também têm distribuições contábeis no cabeçalho da fatura? Em caso afirmativo, essas distribuições contábeis devem estar disponíveis no dispositivo?

    > [!NOTE]
    > Este tópico explica como não editar distribuições contábeis, porque essa funcionalidade não é suportada atualmente para cenários móveis.

-   Os usuários desejarão consultar anexos da fatura no dispositivo?

O design da experiência móvel para aprovações de fatura será diferente, dependendo das respostas a essas perguntas. O objetivo é otimizar a experiência de usuário do processo comercial no celular em uma organização. No restante deste tópico, olharemos duas variações de cenário baseadas em diferentes respostas às perguntas acima. 

Como regra geral, ao trabalhar com o designer móvel, certifique-se de “publicar” as alterações para evitar perda de atualizações.

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a>Como criar um cenário simples de aprovação de fatura para Contoso
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Atributo de cenário</th>
<th>Resposta</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Quais campos do cabeçalho de fatura o usuário desejará ver na experiência móvel, e em que ordem?</td>
<td><ol>
<li>Nome do Fornecedor</li>
<li>Total da fatura</li>
<li>Conta de fatura</li>
<li>Número da fatura</li>
<li>Data da fatura</li>
<li>Descrição da fatura</li>
<li>Data de Vencimento</li>
<li>Moeda da fatura</li>
</ol></td>
</tr>
<tr class="even">
<td>Quais campos das linhas de fatura o usuário desejará ver na experiência móvel, e em que ordem?</td>
<td><ol>
<li>Categoria de compras</li>
<li>Quantidade</li>
<li>Preço unitário</li>
<li>Valor líquido da linha</li>
<li>Valor do 1099</li>
</ol></td>
</tr>
<tr class="odd">
<td>Quantas linhas de fatura estão presentes em uma fatura? Aplicar a regra 80-20 aqui e otimizá-la para 80%.</td>
<td>1</td>
</tr>
<tr class="even">
<td>Os usuários desejarão consultar as distribuições contábeis (codificação de fatura) no dispositivo móvel durante as revisões?</td>
<td>Sim</td>
</tr>
<tr class="odd">
<td>Quantas distribuições contábeis (preço bruto, impostos, encargos, e assim por diante) existem para uma linha de fatura? Novamente, aplique a regra 80-20.</td>
<td>Preço bruto: 2 Imposto: 0 Despesas: 0</td>
</tr>
<tr class="even">
<td>As faturas também têm distribuições contábeis no cabeçalho da fatura? Em caso afirmativo, essas distribuições contábeis devem estar disponíveis no dispositivo?</td>
<td>Não usado</td>
</tr>
<tr class="odd">
<td>Os usuários desejarão consultar anexos da fatura no dispositivo?</td>
<td>Sim</td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a>Criar o espaço de trabalho

1.  Em um navegador, entre no aplicativo.
2.  Após entrar, anexe, append **&mode=mobile** à URL, conforme mostrado no seguinte exemplo e atualize a página: https://&lt;yoururl&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**
3.  Clique no botão **Configurações** (imagem) na parte superior direita da página e clique em **Aplicativo móvel**. O designer de aplicativo móvel deve aparecer apenas enquanto o gravador de tarefas é exibido.
4.  Clique em **Adicionar** para criar um novo espaço de trabalho. Por exemplo, nomeie o espaço de trabalho **Minhas aprovações**.
5.  Insira uma descrição.
6.  Selecionar uma cor do espaço de trabalho. A cor do espaço de trabalho será usada para o estilo geral da experiência móvel deste espaço de trabalho.
7.  Selecionar um ícone para o espaço de trabalho.
8.  Clique em **Concluído**
9.  Clique em **Publicar espaço de trabalho** para salvar as alterações

### <a name="vendor-invoices-assigned-to-me"></a>Faturas de fornecedor atribuídas a mim

A primeira página móvel que você deve criar pela lista de faturas atribuídas ao usuário para revisão. Para criar essa página móvel, use a página **VendMobileInvoiceAssignedToMeListPage**. Para concluir esse procedimento, certifique-se de que pelo menos uma fatura de fornecedor está atribuída a você para revisão e que a linha de fatura tem duas distribuições. Essa configuração atende aos requisitos desse cenário.

1.  Na URL, substitua o nome do item de menu por **VendMobileInvoiceAssignedToMeListPage** para abrir a versão móvel da página da lista **Faturas de fornecedor pendentes atribuídas a mim** no módulo **Contas a pagar**. Dependendo do número de faturas atribuídas a você no sistema, esta página mostrará essas faturas. Para encontrar uma fatura específica, você pode usar o filtro à esquerda. Entretanto, não exigimos uma fatura específica para este exemplo. Nós exigimos apenas algumas faturas atribuídas a você que permitirão que você crie a página móvel. Novas páginas disponíveis foram criadas especificamente para desenvolvimento de cenários móveis para fatura de fornecedor. Portanto, você deve usar essas páginas. A URL deve ser parecida com a URL a seguir e, depois de inserida, a página mostrada na ilustração deverá ser exibida: https://&lt;suaURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile 

    [![Página Faturas de fornecedor atribuídas a mim](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)
    
2.  Clique no botão **Configurações** (imagem) na parte superior à direita da página e clique em **Aplicativo móvel**
3.  Selecione seu espaço de trabalho e clique em **Editar**
4.  Clique em **Adicionar página** para criar a primeira página móvel.
5.  Insira um nome, como **Minhas faturas de fornecedor**, e uma descrição, como **Faturas de fornecedor atribuídas a mim para revisão**.
6.  Clique em **Concluído**.
7.  No desenvolvedor móvel, na guia **Campos**, clique em **Selecionar campos**. As colunas da página de lista devem relembrar a ilustração a seguir. 

    [![Colunas na página Faturas de fornecedor pendentes atribuídas a mim](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)
    
8.  Adicionar as colunas necessárias da página de listagem que deve ser exibida aos usuários na página móvel. A ordem em que você adicionar é a ordem em que os campos serão exibidos ao usuário final. A única maneira de alterar a ordem dos campos será selecionar novamente todos os campos. Com base nos requisitos deste cenário, estes oito campos são necessários. No entanto, alguns usuários podem considerar oito campos muita informação para se ter em um dispositivo móvel. Portanto, mostraremos apenas os campos mais importantes na exibição de lista móvel. Os demais campos aparecerão nos detalhes que criaremos posteriormente. Por hora, adicionaremos os campos a seguir. Clique no sinal de mais (**+**) nessas colunas para adicionar a página móvel.
    - Nome do Fornecedor
    - Total da fatura
    - Conta de fatura
    - Número da fatura
    - Data da fatura

    Depois dos campos serem adicionados, a página móvel deve ser semelhante à ilustração a seguir. 
    
    [![Página após os campos serem adicionados](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)

9.  Você também deve adicionar as seguintes colunas agora, para que possamos habilitar ações de fluxo de trabalho posteriormente.
    - Exibir tarefa concluída
    - Exibir tarefa delegada
    - Exibir tarefa de recuperação
    - Exibir tarefa de rejeição
    - Exibe tarefa de conclusão de solicitação
    - Exibir tarefa de reenvio

10. Clique em **Concluído** para sair do modo de edição.
11. Clique em **Voltar** e depois em **Concluído** para sair da área de trabalho
12. Clique em **Publicar espaço de trabalho** para salvar seu trabalho.
13. Habilite **Exibir total de fatura na lista de faturas de fornecedor pendentes** no formulário de parâmetros de contas a pagar em **Fatura**. Observe que, apenas ao habilitar esse parâmetro, os totais de fatura serão calculados para serem exibidos na página de listagem de faturas de fornecedor pendentes. Este é um novo recurso como parte do pré-requisito do hot fix 3208224.

### <a name="vendor-invoice-details"></a>Detalhes da fatura do fornecedor

Para criar a página de detalhes da fatura para dispositivos móveis, use a página **VendMobileInvoiceHeaderDetails**. Observe que, dependendo do número de faturas que você possui no sistema, esta página exibe fatura mais antiga (a fatura criada primeiro.) Para encontrar uma fatura específica, você pode usar o filtro à esquerda. Entretanto, não exigimos uma fatura específica para este exemplo. Nós exigimos apenas alguns dados de fatura para que possamos criar a página móvel. 

[![Página do fluxo de trabalho](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)

1. Na URL, substitua o nome do item de menu por **VendMobileInvoiceHeaderDetails** para abrir o formulário

2. Abra o criador móvel a partir do botão **Configurações** (imagem).

3. Clique no botão **Editar** para iniciar o modo de edição no espaço de trabalho.

4. Selecione a página **Minhas fatura de fornecedor** que você criou anteriormente e clique em **Editar**.

5. Na guia **Campos**, clique no cabeçalho da coluna **Grade**.

6. Clique em **Propriedades &gt; Adicionar página**. **Observação:** Quando clicar no cabeçalho **Grade** e adicionar uma página, a relação com a página de detalhes é estabelecida automaticamente.

7. Insira um título de página, como **Detalhes de fatura**, e uma descrição, como **Exibir cabeçalho de fatura e detalhes de linha**.

8. Clique em **Selecionar campos**. Observe que, a ordem em que você adicionar é a ordem em que os campos serão exibidos para o usuário final. A única maneira de alterar a ordem dos campos será selecionar novamente todos os campos. 

9. Adicione os campos a seguir a partir do cabeçalho baseado nos requisitos deste cenário:
   - Nome do Fornecedor
   - Total da fatura
   - Conta de fatura
   - Número da fatura
   - Data da fatura
   - Descrição da fatura
   - Data de Vencimento
   - Moeda da fatura

10. Adicione os seguintes campos das linhas da grade na página:
    - Categoria de compras
    - Quantidade
    - Preço unitário
    - Valor líquido da linha
    - Valor do 1099

11. Depois que todos os campos das duas etapas anteriores terem sido adicionados, clique em **Concluído**. A página deve ser semelhante à ilustração a seguir.
    
    [![Página após os campos serem adicionados](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)

12. Clique em **Concluído** para sair do modo de edição.

13. Clique em **Voltar** e depois em **Concluído** para sair da área de trabalho

14. Clique em **Publicar espaço de trabalho** para salvar seu trabalho

### <a name="workflow-actions"></a>Ações de fluxo de trabalho

Para adicionar ações de fluxo de trabalho, use a página **VendMobileInvoiceHeaderDetails**. Para abrir essa página, substitua o nome do item de menu na URL, como você fez anteriormente. Para abrir o criador móvel a partir do botão **Configurações** (imagem). Rastreie essas etapas para adicionar ações de fluxo de trabalho na página de detalhes. É necessário ter faturas atribuídas a você que estão no estado apropriado para realizar ações de fluxo de trabalho disponíveis a você e que você criará.

#### <a name="record-workflow-actions"></a>Registro de ações de fluxo de trabalho
1.  Clique no botão **Editar** para iniciar o modo de edição no espaço de trabalho.
2.  Selecione a página **Detalhes de fatura** que você criou anteriormente e clique em **Editar**.
3.  Na guia **Ações**, clique em **Adicionar ação**.
4.  Insira um título de ação, como **Aprovar** e uma descrição como **Aprovação de fatura**. Observe que o título da ação inserido aqui se transforma no nome da ação exibido para o usuário no aplicativo móvel.
5.  Clique em **Concluído**.
6.  Clique em **Selecionar campos**.
7.  Passe pelo processo de fluxo de trabalho na página **VendMobileInvoiceHeaderDetails** e complete a ação que deseja registrar. Verifique se você inseriu os comentários de fluxo de trabalho durante esse processo, para que um campo de comentários também seja incluído na experiência móvel.
8.  Depois da ação de fluxo de trabalho ser executada, clique em **Concluído** para concluir a tarefa Selecionar campos.
9.  Clique em **Concluído** para sair do modo de edição.
10. Clique em **Voltar** e depois em **Concluído** para sair da área de trabalho
11. Clique em **Publicar espaço de trabalho** para salvar seu trabalho
12. Repita as etapas anteriores para registrar todas as ações necessárias do fluxo de trabalho. 

#### <a name="create-a-js-file"></a>Crie um arquivo .js
1. Abra o Bloco de Notas ou Visual Studio e cole o código a seguir. Salve o arquivo como .js. Este código faz o seguinte:
    - Oculta colunas relacionadas a fluxo de trabalho extra que foram adicionadas anteriormente na página de listagem móvel. Nós adicionamos essas colunas de forma que o aplicativo tenha essas informações no contexto e possa executar a próxima etapa.
    - Com a etapa do fluxo de trabalho ativa, aplique a lógica para mostrar somente aquelas ações.

    > [!NOTE]
    > O nome das páginas e outros controles no código devem ser iguais aos nomes no espaço de trabalho.

    ```javascript
    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                       var showRejectControl = Boolean(rejectControl == 1);
                      var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                     metadataService.configureAction('Resubmit', { visible: showResubmitControl });
                   }
                 },
           };
        }
    ```

2.  Carregue o arquivo do código ao espaço de trabalho selecionando a guia **Lógica**.
3.  Clique em **Concluído** para sair do modo de edição.
4.  Clique em **Voltar** e depois em **Concluído** para sair da área de trabalho
5.  Clique em **Publicar espaço de trabalho** para salvar seu trabalho

### <a name="vendor-invoice-attachments"></a>Anexos da fatura de fornecedor

1. Clique no botão **Configurações** (imagem) na parte superior à direita da página e clique em **Aplicativo móvel**

2. Clique no botão **Editar** para iniciar o modo de edição no espaço de trabalho.

3. Selecione a página <strong>Detalhes da fatura **criada anteriormente e clique em **Editar</strong>.

4. Defina a opção **Gerenciamento de documento** para **Sim** como exibido abaixo. **Observação:** Se não houver requisitos para exibir os anexos no dispositivo móvel, você pode deixar essa opção definida como **Não**, que é a configuração padrão.
   
   ![Gerenciamento de documentos](./media/docmanagement-216x300.png)

5. Clique em **Concluído** para sair do modo de edição.

6. Clique em **Voltar** e depois em **Concluído** para sair da área de trabalho

7. Clique em **Publicar espaço de trabalho** para salvar seu trabalho

### <a name="vendor-invoice-line-distributions"></a>Distribuições de linha de fatura de fornecedor

Os requisitos para este cenário confirmam que haverá apenas distribuições ao nível de linha e que uma fatura terá sempre apenas uma linha. Como esse cenário é simples, a experiência de usuário no dispositivo móvel deve ser suficientemente simples para o usuário não ter de fazer busca detalhada de vários níveis para exibir as distribuições. As faturas de fornecedor incluem a opção de mostrar todas as distribuições do cabeçalho de fatura. Essa experiência é o que precisamos para o cenário móvel. Portanto, usaremos a página **VendMobileInvoiceAllDistributionTree** para criar essa parte do cenário móvel. 

> [!NOTE] 
> Saber os requisitos nos ajuda a decidir qual página específica usar e quão exatamente otimizar a experiência móvel para o usuário quando criarmos o cenário. No segundo cenário, usaremos uma página diferente para mostrar as distribuições, pois as necessidades para esse cenário são diferentes.

1.  Na URL, substitua o nome do item de menu, como fez anteriormente. A página que aparece deve ser semelhante à ilustração a seguir.

    [![Página de todas as distribuições](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)

2.  Abra o criador móvel a partir do botão **Configurações** (imagem).

3.  Clique no botão **Editar** para iniciar o modo de edição no espaço de trabalho. **Observação:** Você verá que duas novas páginas foram criadas automaticamente. O sistema cria essas páginas porque você ativou o gerenciamento de documentos na seção anterior. Você pode ignorar essas novas páginas.

4.  Clique em **Adicionar página**.

5.  Insira um título de página, como **Exibir contabilidade**, e uma descrição como **Exibir contabilidade da fatura**.

6.  Clique em **Concluído**.

7.  Na guia **Campos**, clique em **Selecionar campos**, selecione os campos a seguir das páginas de distribuição e depois clique em **Concluído**:
    1.  Valor
    2.  Moeda
    3.  Conta contábil

    > [!NOTE] 
    > Não selecionamos a coluna **Descrição** da grade de distribuições porque os requisitos desse cenário confirmaram que o preço bruto é o único valor que existirá para as distribuições. Portanto, o usuário não exigirá outro campo para determinar o tipo de valor para o qual a distribuição foi criada. No entanto, nesse cenário, nós **usaremos** essa informação porque os requisitos desse cenário especificam que outros tipos de valores têm distribuições (por exemplo, imposto).

8.  Clique em **Concluído** para sair do modo de edição.

9.  Clique em **Voltar** e depois em **Concluído** para sair da área de trabalho

10. Clique em **Publicar espaço de trabalho** para salvar seu trabalho

#### <a name="adding-navigation-to-view-accounting-page"></a>Adicionando navegação à página "Exibir contabilidade"

A página móvel **Exibir contabilidade** não está vinculada atualmente a quaisquer páginas móveis que criamos até agora. Como o usuário deve poder navegar até a página **Exibir contabilidade** da página **Detalhes de fatura** no dispositivo móvel, devemos fornecer navegação da página **Detalhes da fatura** para a página **Exibir contabilidade**. Nós estabelecemos essa navegação usando a lógica adicional por JavaScript.

1.  Abra o arquivo .js criado anteriormente e adicione linhas realçadas no código a seguir. Este código faz duas coisas:
    1.  Ajuda a garantir que os usuários não consigam navegar diretamente do espaço de trabalho até a página **Exibir contabilidade**.
    2.  Estabelece o controle de navegação da página **Detalhes de fatura** até a página **Exibir contabilidade**.

    > [!NOTE] 
    > O nome das páginas e outros controles no código devem ser iguais aos nomes no espaço de trabalho.

    ```javascript
    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
                   // Hide pages not applicable for root navigation
                   metadataService.hideNavigation('View-accounting');
                   //Link to view accounting
                   metadataService.addLink('Invoice-details', 'View-accounting', 'View-accounting-nav-control', 'View accounting', true);
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                     var showRejectControl = Boolean(rejectControl == 1);
                       var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                       metadataService.configureAction('Resubmit', { visible: showResubmitControl });
        }
                 },
           };
        }
    ```
    
2.  Carregue o arquivo do código ao espaço de trabalho selecionando a guia **Lógica** para sobrescrever o código a seguir.
3.  Clique em **Concluído** para sair do modo de edição.
4.  Clique em **Voltar** e depois em **Concluído** para sair da área de trabalho
5.  Clique em **Publicar espaço de trabalho** para salvar seu trabalho

### <a name="validation"></a>Validação

No dispositivo móvel, abra o aplicativo e conecte-se à sua instância. Certifique-se de que você está conectado à empresa onde as faturas de fornecedor são atribuídas a você para revisão. Você deve ser capaz de executar as seguintes ações:

-   Consulte o espaço de trabalho **Minhas aprovações**.
-   Entre na área de trabalho **Minhas aprovações** e consulte a página **Minhas faturas de fornecedor**.
-   Entre na página **Minhas faturas de fornecedor** e consulte a lista de faturas atribuídas a você.
-   Entre em uma das faturas, e consulte os detalhes do cabeçalho de fatura e os detalhes da linha.
-   Na página de detalhes, consulte um link para anexos e use esse link para navegar à lista de anexos e ver os anexos.
-   Na página de detalhes, consulte um link para a página **Exibir contabilidade** e use esse link para navegar à página de distribuições e ver as distribuições.
-   Na página de detalhes, clique no menu **Ações** na parte inferior e realize ações de fluxo de trabalho que são aplicáveis à etapa de fluxo de trabalho.

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a>Como criar um cenário complexo de aprovação de fatura para Fabrikam
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Atributo de cenário</th>
<th>Resposta</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Quais campos do cabeçalho de fatura o usuário desejará ver na experiência móvel, e em que ordem?</td>
<td><ol>
<li>Nome do Fornecedor</li>
<li>Valor da fatura</li>
<li>Conta de fatura</li>
<li>Número da fatura</li>
<li>Data da fatura</li>
<li>Descrição da fatura</li>
<li>Data de Vencimento</li>
<li>Moeda da fatura</li>
</ol></td>
</tr>
<tr class="even">
<td>Quais campos das linhas de fatura o usuário desejará ver na experiência móvel, e em que ordem?</td>
<td><ol>
<li>Categoria de compras</li>
<li>Quantidade</li>
<li>Preço unitário</li>
<li>Valor líquido da linha</li>
<li>Valor do 1099</li>
</ol></td>
</tr>
<tr class="odd">
<td>Quantas linhas de fatura estão presentes em uma fatura? Aplicar a regra 80-20 aqui e otimizá-la para 80%.</td>
<td>5</td>
</tr>
<tr class="even">
<td>Os usuários desejarão consultar as distribuições contábeis (codificação de fatura) no dispositivo móvel durante as revisões?</td>
<td>Sim</td>
</tr>
<tr class="odd">
<td>Quantas distribuições contábeis (preço bruto, impostos, encargos, e assim por diante) existem para uma linha de fatura? Novamente, aplique a regra 80-20.</td>
<td>Preço bruto: 2 Imposto: 2 Despesas: 2</td>
</tr>
<tr class="even">
<td>As faturas também têm distribuições contábeis no cabeçalho da fatura? Em caso afirmativo, essas distribuições contábeis devem estar disponíveis no dispositivo?</td>
<td>Não usado</td>
</tr>
<tr class="odd">
<td>Os usuários desejarão consultar anexos da fatura no dispositivo?</td>
<td>Sim</td>
</tr>
</tbody>
</table>

### <a name="next-steps"></a>Próximas etapas

As variações a seguir podem ser realizadas para o cenário 1, com base nos requisitos do cenário 2. Você pode usar esta seção para melhorar a sua experiência com o aplicativo móvel.

1.  Como mais linhas de fatura são esperadas no cenário 2, as alterações a seguir para a criação ajudarão a otimizar a experiência do usuário no dispositivo móvel:
    1.  Em vez de exibir linhas na página de detalhes (como no cenário 1), os usuários podem escolher exibir linhas em uma página móvel separada.
    2.  Como mais de uma linha de fatura é esperada neste cenário, se a página **VendMobileInvoiceAllDistributionTree** for usada para criar a página de distribuições para dispositivo móvel (como no cenário 1), pode ser confuso para o usuário correlacionar as linhas de distribuição. Portanto, use a página **VendMobileInvoiceLineDistributionTree** para criar a página de distribuições.
    3.  Idealmente, as distribuições devem ser mostradas no contexto de uma linha de fatura neste cenário. Portanto, certifique-se de que o usuário pode entrar em uma linha para exibir a página de distribuições. Use o recurso de link de página para estabelecer a entrada, assim como fez no cabeçalho e nas páginas de detalhes no cenário 1.

2.  Como mais de um tipo de valor é esperado nas distribuições no cenário 2 (impostos, cobranças e assim por diante), será útil exibir a descrição do tipo de valor. (Omitimos estas informações no cenário 1.)






[!INCLUDE[footer-include](../../includes/footer-banner.md)]