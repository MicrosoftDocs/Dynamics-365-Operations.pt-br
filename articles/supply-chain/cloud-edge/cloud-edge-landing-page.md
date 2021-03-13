---
title: Unidades de escala de nuvem e de borda para cargas de trabalho de fabricação e depósito
description: Este tópico oferece informações sobre unidades de escala de nuvem e de borda para cargas de trabalho de gerenciamento de fabricação e depósito.
author: cabeln
manager: ''
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: cabeln
ms.search.validFrom: 2020-09-23
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 28301cdfb86d00ea6f04e996fe7fb1485e83b2d4
ms.sourcegitcommit: 289e9183d908825f4c8dcf85d9affd4119238d0c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104955"
---
# <a name="cloud-and-edge-scale-units-for-manufacturing-and-warehouse-management-workloads"></a>Unidades de escala de nuvem e de borda para cargas de trabalho de fabricação e depósito

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

As unidades de escala de nuvem e de borda permitem a distribuição de cargas de trabalho de chão de fábrica e de execução de depósito entre diferentes ambientes. Essa funcionalidade pode ajudar a melhorar o desempenho, prevenir interrupções de serviço e maximizar o tempo de atividade. Ela é fornecido pelos seguintes suplementos:

- Suplemento de unidade de escala de nuvem para o Dynamics 365 Supply Chain Management
- Suplemento de unidade de escala de borda para o Dynamics 365 Supply Chain Management

As empresas que trabalham com fabricação e distribuição devem ser capazes de executar os principais processos comerciais 24/7, sem interrupção e em grande escala. As unidades de escala de nuvem e de borda permitem que as empresas executem os principais processos de fabricação e de depósito de missão crítica sem interrupção, mesmo quando enfrentam problemas ocasionais de conectividade de rede ou de latência.

## <a name="public-preview-information"></a>Informações da versão preliminar pública

A versão preliminar oferece um ambiente que funciona como um hub baseado na nuvem do ambiente Dynamics 365 Supply Chain Management e um ambiente que funciona como uma unidade de escala de nuvem.

<!-- You will also be able to use Local Business Data (LBD) to configure an on-premises environment as an edge scale unit for the hub you received as part of the preview program.-->

### <a name="preview-availability"></a>Visualizar disponibilidade

A versão preliminar das unidades de escala de nuvem e de borda é disponibilizada para clientes existentes do Supply Chain Management em outubro de 2020.

Para acessar a versão prévia de outubro 10.0.15/Platform update 39 para implantação no ambiente do [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/v2), você deve fazer parte da prévia do programa de adoção antecipada (também conhecida como PEAP) para o Supply Chain Management. Você poderá participar do PEAP se já for membro do [Dynamics Insider Program](https://experience.dynamics.com/insider) mais amplo. Basta selecionar o programa específico chamado "Finance and Operations: prévia do programa de adoção antecipada (PEAP)".

> [!IMPORTANT]
> O recurso de unidade de escala para o Supply Chain Management estará disponível somente se você concordar com os [termos de exibição de nuvem e de borda do Finance and Operations](https://Aka.ms/SCMCnETerms).

### <a name="data-processing-for-the-preview"></a>Processamento de dados para a versão preliminar

Durante a versão preliminar pública, alguns serviços de gerenciamento só serão hospedados nos Estados Unidos. No entanto, quando o recurso for disponibilizado no mercado, esses serviços de gerenciamento estarão disponíveis em todas as regiões geográficas com suporte do Supply Chain Management. Isso afeta a transferência e o armazenamento de informações administrativas usadas pelo gerente de unidade de escala, incluindo:

- Nomes e IDs de locatários
- IDs de projeto LCS
- Emails do administrador usados para se conectar
- IDs de ambiente para unidades de hub e escala
- Configurações de carga de trabalho
- Métricas coletadas (como latência e taxa de transferência) que são exibidas na página análise de mapa

Os dados transferidos e armazenados nos data centers dos EUA serão excluídos quando os ambientes de visualização forem desligados.

### <a name="sign-up-for-the-preview"></a>Inscrever-se na versão prévia

Para inscrever-se na versão preliminar de nuvem e de borda para o Supply Chain Management, sua organização já deve ter um ambiente de nuvem dinâmico do Supply Chain Management.

Os recursos da unidade de escala estão atualmente em versão preliminar pública. Ao se inscrever, você deve usar uma conta de usuário no locatário específico. Você também deve ser um proprietário de projeto ou um administrador de ambiente no LCS para um projeto LCS ativo do Dynamics 365 nesse locatário.

Ao se inscrever na versão preliminar, você selecionará um locatário e passará pelas etapas de inscrição. Assim que a Microsoft puder alocar o recurso de versão preliminar, enviaremos um email que inclui os detalhes de provisionamento e os códigos promocionais para dois ambientes (um hub e uma unidade de escala) para o projeto LCS adequado. Você poderá implantar os dois ambientes como ambientes de área restrita de nível 2. Esses ambientes serão válidos 60 dias após a data de criação dos códigos promocionais. Você não deverá usar os dois ambientes até que a etapa descrita no próximo parágrafo seja preenchida.

Depois de confirmar com a Microsoft que os dois ambientes foram implantados usando os códigos promocionais, um dos ambientes será configurado para funcionar como um hub e o outro para funcionar como uma unidade de escala. Você poderá configurar as unidades de escala e implantar cargas de trabalho selecionadas de gerenciamento de depósito e fabricação por meio do [portal do Gerente de Unidade de Escala](https://aka.ms/SCMSUM).

Os ambientes de versão preliminar serão excluídos automaticamente após 60 dias. No entanto, eles poderão ser excluídos mais cedo se parecer que não estão em uso. Após a exclusão dos ambientes de visualização, você poderá inscrever-se e candidatar-se a uma nova implantação de versão prévia.

Para inscrever-se na versão prévia, acesse o [portal do Gerente de Unidade de Escala](https://aka.ms/SCMSUM).

### <a name="limitations-that-apply-during-the-preview-period"></a>Limitações que se aplicam durante o período de versão prévia

> [!IMPORTANT]
> Para a fase inicial do programa de visualização deste recurso, a Microsoft dá suporte somente a hubs que têm unidades de escala de nuvem, e não hubs com unidades de escala de grade. As unidades de escala de grade são instaladas localmente e espera-se que estejam disponíveis durante uma fase futura do programa.

Como as unidades de escala de nuvem e de borda são recursos de visualização, os serviços relacionados a elas estão disponíveis no momento em países e regiões limitados. Ao habilitar unidades de escala de nuvem e de borda, você afirma que entendeu que alguns dados relacionados à configuração e ao processamento de unidades de escala de nuvem e de borda podem ser armazenados em um data center localizado nos Estados Unidos. Ao habilitar unidades de escala de nuvem e de borda, você também concorda com os [termos de exibição de nuvem e de borda do Finance and Operations](https://Aka.ms/SCMCnETerms). Para saber mais sobre unidades de escala de nuvem e de borda, consulte a [documentação](https://aka.ms/scmcne).

Sua privacidade é importante para a Microsoft. Para saber mais, leia nossa [política de privacidade](https://aka.ms/privacy).

> [!IMPORTANT]
> Algumas funcionalidades comerciais não têm suporte total na versão preliminar pública quando cargas de trabalho são usadas em unidades de escala. Para obter mais informações sobre cargas de trabalho funcionais, consulte as seções mais adiante neste tópico.

## <a name="scale-units-and-dedicated-workloads"></a>Unidades de escala e cargas de trabalho dedicadas

:::image type="content" source="./media/cloud_edge-HeroDiagram.png" alt-text="Dynamics 365 com unidades de escala":::

Unidades de escala estendem o ambiente do hub do Supply Chain Management central adicionando capacidade de processamento dedicado. As unidades de escala podem ser executadas na nuvem. Como alternativa, elas podem ser executadas na borda de instalações locais. As unidades de escala podem ser temporariamente desconectadas do ambiente de hub. Quando estiverem conectadas, as unidades de escala receberão todas as informações necessárias para executar o processamento dedicado de cargas de trabalho atribuídas.

:::image type="content" source="media/cloud_edge-previewoptions.png" alt-text="Opções da unidade de escala na versão preliminar pública":::

Para a versão preliminar pública, você pode configurar um ambiente de hub com cargas de trabalho selecionadas em uma unidade de escala de nuvem usando o portal do Gerente de Unidade de Escala. Participantes de versão preliminar com acesso a um ambiente local de dados comerciais locais (LBD) também podem configurar o ambiente LBD como uma unidade de escala de borda.

Uma carga de trabalho é um conjunto definido de funcionalidades comerciais que podem ser fatoradas e delegadas a uma unidade de escala. No momento, a versão prévia de recursos apresenta dois tipos de cargas de trabalho:

- Execução de fabricação
- Gerenciamento de depósito

Você pode atribuir um de cada tipo de carga de trabalho por unidade de escala. 

### <a name="dedicated-manufacturing-execution-workload-capabilities-in-a-scale-unit"></a>Recursos dedicados de carga de trabalho de execução de fabricação em uma unidade de escala

Para a execução de fabricação, as unidades de escala de nuvem e de borda fornecem os seguintes recursos, mesmo quando as unidades de borda não estão conectadas à nuvem:

- Os operadores de máquina e os supervisores de chão de fábrica podem acessar o plano de produção operacional.
- Os operadores de máquina podem manter o plano atualizado ao executar trabalhos de fabricação discretos e de processo.
- O supervisor de chão de fábrica pode ajustar o plano operacional.
- Os trabalhadores podem acessar o tempo e a presença de entrada e de saída na borda para garantir o cálculo correto do pagamento do trabalhador.

Para obter mais informações, consulte os [detalhes da carga de trabalho da unidade de escala de fabricação](cloud-edge-workload-manufacturing.md).

### <a name="dedicated-warehouse-management-workload-capabilities-in-a-scale-unit"></a>Recursos dedicados de carga de trabalho de gerenciamento de depósito em uma unidade de escala

Para gerenciamento de depósito, as unidades de escala de nuvem e de borda fornecem os seguintes recursos, mesmo quando as unidades de borda não estão conectadas à nuvem:

- O processamento de métodos de ciclo selecionados é habilitado para ordens de venda e reabastecimento de demanda.
- Os trabalhadores de depósito podem executar o trabalho de depósito de reabastecimento de demanda e vendas usando o aplicativo de depósito.
- Os trabalhadores de depósito podem consultar o estoque disponível usando o aplicativo de depósito.
- Os trabalhadores de depósito podem criar e executar movimentações de estoque usando o aplicativo de depósito.
- Os trabalhadores de depósito podem registrar ordens de compra e fazer armazenamento usando o aplicativo de depósito.

Para obter mais informações, consulte os [detalhes da carga de trabalho da unidade de escala de depósito](cloud-edge-workload-warehousing.md).

## <a name="onboard-scale-units-for-your-supply-chain-management-environment"></a>Unidades de escala integrada para o ambiente do Supply Chain Management

### <a name="deploy-the-preview-for-cloud-and-edge-scale-units"></a>Implantar a versão preliminar para unidades de escala de nuvem e de borda

A ilustração a seguir mostra o fluxo de inscrição e provisionamento para a versão preliminar pública de unidades de escala de nuvem.

:::image type="content" source="media/cloud_edge-previewsignup.png" alt-text="Visualizar etapas de inscrição":::

### <a name="select-your-lcs-project-tenant-and-the-detailed-preview-process"></a>Selecione o locatário de projeto LCS e o processo de visualização detalhado

Na versão preliminar pública, o [portal do Gerente de Unidade de Escala](https://aka.ms/SCMSUM) mostra a lista de locatários dos quais sua conta faz parte e onde você é um administrador proprietário ou de ambiente para um projeto LCS.

Se o locatário que você está procurando não estiver nessa lista, acesse [LCS](https://lcs.dynamics.com/v2) e verifique se você é um administrador de ambiente ou um proprietário de projeto do projeto LCS desse locatário. Observe que somente contas do Azure Active Directory (Azure AD) do locatário selecionado estão autorizadas a concluir a experiência de inscrição.

> [!NOTE]
> Após aplicar alterações ao LCS, poderá levar até 30 minutos para que a lista de locatários reflita as alterações.

Para cada locatário, a lista mostra o status de inscrição.

:::image type="content" source="media/cloud_edge-Signup1.png" alt-text="Opção de inscrição para um locatário":::

Selecione o link **Clique aqui para inscrever-se** para inscrever o locatário do LCS para participar da versão preliminar. Você deve aceitar os termos. Você também deve fornecer um endereço de email comercial em que a Microsoft pode enviar comunicações relacionadas ao processo de inscrição de versão prévia.

:::image type="content" source="media/cloud_edge-Signup2.png" alt-text="Envio de inscrição para um locatário":::

A Microsoft revisará a solicitação e informará sobre as próximas etapas enviando um email para o endereço fornecido no formulário de inscrição.

Após ter acesso ao programa de versão preliminar, você receberá dois códigos promocionais para o projeto LCS. Agora você pode usar esses códigos promocionais para implantar dois ambientes em LCS. Os ambientes devem usar o PEAP versão 10.0.15 ou posterior. Ao terminar de aplicar os códigos promocionais, notifique a Microsoft (conforme orientado) para que possamos concluir a habilitação dos ambientes para as versões prévias do recurso. A Microsoft permitirá que você saiba quando esta etapa de configuração foi concluída.

Você pode começar a configurar unidades de escala e cargas de trabalho no ambiente de visualização.

> [!IMPORTANT]
> Ao configurar unidades de escala de nuvem, você pode [executar todas as etapas necessárias no portal do Gerente de Unidade de Escala](#scale-unit-manager-portal).
<!-- 
> If want to use edge scale units with your preview deployment, you must do all scale unit configuration in the user interface on the hub as described in [Configure the hub environment for use with edge scale units](cloud-edge-edge-scale-units-lbd.md#configure-the-hub-environment). You can't use Scale Unit Manager portal if you include an edge scale unit. -->

### <a name="manage-cloud-scale-units-and-workloads-by-using-the-scale-unit-manager-portal"></a><a name="scale-unit-manager-portal"></a>Gerenciar unidades de escala de nuvem e cargas de trabalho usando o portal de Gerente de Unidade de Escala

Acesse o [portal do Gerente e Unidade de Escala](https://aka.ms/SCMSUM) e entre usando sua conta de locatário. Na página **Configurar unidades de escala**, você poderá adicionar um ambiente de hub, caso ainda não esteja listado. Você pode selecionar o hub a ser configurado com unidades de escala e cargas de trabalho.

:::image type="content" source="media/cloud_edge-Manage.png" alt-text="Experiência de gerenciamento de unidade de escala e carga de trabalho":::

Para adicionar uma ou mais unidades de escala que estejam disponíveis em sua topologia, selecione **Adicionar unidades de escala**. Na versão preliminar, você verá a unidade de escala de nuvem implantada a partir de um dos códigos promocionais recebidos como parte do programa de visualização.

<!--  [!IMPORTANT]
> In the public preview, the Scale Unit Manager portal shows the cloud scale unit that you received as part of the preview program. Any edge scale unit that you created based on an LBD configuration can't be managed in the Scale Unit Manager portal yet. For configuration details, see [Deploy custom edge scale units on custom hardware using LBD](cloud-edge-edge-scale-units-lbd.md) -->

Na guia **Cargas de trabalho definidas**, use o botão **Criar carga de trabalho** para adicionar um gerenciamento de depósito ou uma carga de trabalho de execução de fabricação a uma das unidades de escala. Para cada carga de trabalho, você deve especificar o contexto dos processos que serão propriedade da carga de trabalho. Para cargas de trabalho de gerenciamento de depósito, o contexto é um depósito específico em um site e uma entidade legal específicos. Para cargas de trabalho de execução de fabricação, o contexto é um site específico em uma entidade legal.

:::image type="content" source="media/cloud_edge-DefineWorkload.png" alt-text="Criação de carga de trabalho":::

> [!IMPORTANT]
> O portal do Gerente de Unidade de Escala na versão preliminar não permite remover cargas de trabalho de unidades de escala ou cancelar a atribuição de uma unidade de escala de um hub após a atribuição ser feita. Se for necessário remover uma atribuição, contate a pessoa de contato para gerenciamento do programa de visualização.

<!-- ### Create an edge scale unit using your custom on-premises hardware appliance

In the public preview, you can create on-premises edge scale units on your custom hardware using the LBD environments. For details, see [Deploy custom edge scale units on custom hardware using LBD](cloud-edge-edge-scale-units-lbd.md). -->
