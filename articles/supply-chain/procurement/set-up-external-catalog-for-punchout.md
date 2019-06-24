---
title: Configurar um catálogo externo para compras eletrônicas de PunchOut
description: Este tópico descreve o uso de um catálogo externo ou catálogo de pontapé para coletar informações de cotação de um fornecedor e adicioná-lo a uma requisição.
author: mkirknel
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 39baa331120d765543c3cf662ce53d2bcfe404ab
ms.sourcegitcommit: 574d4dda83dcab94728a3d35fc53ee7e2b90feb0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/22/2019
ms.locfileid: "1595602"
---
# <a name="set-up-an-external-catalog-for-punchout-eprocurement"></a>Configurar um catálogo externo para compras eletrônicas de PunchOut

[!include [banner](../includes/banner.md)]

Ao usar o catálogo externo, você pode garantir que as informações de produtos e preços que você processar posteriormente no Dynamics 365 for Finance and Operations, julho de 2017, são precisas e atualizadas. A requisição pode então ser aprovada e convertida em uma ordem de compra e um pedido pode ser colocado no fornecedor.

Quando o catálogo externo for configurado e um funcionário estiver preparando uma requisição, haverá uma opção para redirecionar para um site externo, o catálogo externo e retornar o carrinho de compras que foi criado no site externo. Esta comunicação é baseada no protocolo cXML e deve ser configurada entre os sistemas de compra e a organização de venda.

Para configurar a comunicação, o seu fornecedor deve fornecer peças de informação para você usar na configuração do catálogo externo, como identidade, domínio da empresa compradora, por exemplo, "DUNS" e "Número DUNS", credenciais e o URL para acessar o catálogo dos fornecedores.

## <a name="setting-up-an-external-catalog"></a>Configurando um catálogo externo

O catálogo externo deve permitir que um funcionário que insere uma requisição de compra seja redirecionado para um site externo para selecionar produtos. Os produtos que o funcionário seleciona do catálogo externo são devolvidos ao Dynamics 365 for Finance and Operations com informações de preços atualizadas e, a partir daqui, elas podem ser adicionadas à requisição de compra. A intenção não é permitir que os funcionários façam um pedido no site externo. Ao configurar o catálogo externo, você precisa ter certeza de que o objetivo do site acessível pelo catálogo externo seja coletar informações de cotação e não abrir uma ordem real.

### <a name="to-set-up-an-external-vendor-catalog-complete-the-following-tasks"></a>Para configurar um catálogo externo de fornecedor, conclua as tarefas a seguir:

1. Configurar uma hierarquia de categorias de compras. Para obter mais informações, consulte [Configurar políticas para hierarquias de categoria de aquisição](tasks/set-up-policies-procurement-category-hierarchies.md).
2. Registre o fornecedor no Finance and Operations. Antes de estabelecer as configurações para acessar o catálogo externo de um fornecedor, é necessário configurar o fornecedor e o contato do fornecedor no Microsoft Dynamics 365. O catálogo externo do fornecedor também deve ser adicionado à categoria de compras selecionada. Para obter mais informações sobre como registrar fornecedores no Microsoft Dynamics 365, consulte [Gerenciar usuários de colaboração do fornecedor](manage-vendor-collaboration-users.md). Para obter informações sobre como atribuir fornecedores a uma categoria de aquisição, consulte [Aprovar fornecedores para categorias específicas de aquisição](tasks/approve-vendors-specific-procurement-categories.md).
3. Certifique-se de que as unidades de medida e a moeda que o fornecedor usa estejam configuradas. Para obter informações sobre como criar uma unidade de medida, consulte [Gerenciar unidades de medida](../pim/tasks/manage-unit-measure.md).
4. Configurar o catálogo externo de fornecedor usando os requisitos do site do catálogo externo do fornecedor. Para obter mais detalhes sobre essa tarefa, consulte [Configurar o catálogo de fornecedor externo](#configure-the-external-vendor-catalog).
5. Teste as configurações do catálogo externo do fornecedor para verificar se as configurações são válidas e se você pode acessar o catálogo externo do fornecedor. Use a ação **Validar configurações** para validar a mensagem de configuração de solicitação que você definiu. Esta mensagem deve fazer com que o site do catálogo externo dos vendedores seja aberto em uma janela do navegador. Durante a validação, você não pode encomendar itens e serviços do fornecedor. Para encomendar itens e serviços, você deve acessar o catálogo do fornecedor de uma requisição de compra.
6. Ative o catálogo externo usando o botão **Ativar catálogo** na página **Catálogos externos**. O catálogo externo deve ser ativado antes que os funcionários possam usá-lo. Você pode desativar o catálogo externo a qualquer momento.


## <a name="configure-the-external-vendor-catalog"></a>Configure o catálogo do fornecedor externo

Esta seção fornece mais detalhes sobre a tarefa 4 na seção anterior.

1. Digite um nome e uma descrição para o catálogo externo do fornecedor. O nome que você inseriu aparecerá no carrinho que representa o catálogo externo que é mostrado aos funcionários que criam uma requisição. Os funcionários podem clicar no carrinho para abrir o catálogo no site do catálogo externo do fornecedor.
2. Adicione uma imagem usando a ação **Imagem externa de catálogo**. A imagem aparecerá no carrinho que representa o catálogo externo que é mostrado aos funcionários que criam uma requisição. Observe que a largura e a altura da imagem devem ser iguais. Caso contrário, a imagem não será exibida corretamente.
3. Selecione se o site do catálogo externo do fornecedor deve aparecer na mesma janela do navegador como aquele em que o funcionário criou a requisição ou se deve abrir em uma nova janela.
4. Selecione o fornecedor para o catálogo. Na lista **Entidades legais**, há uma linha para cada entidade legal na qual o fornecedor está configurado. Para permitir que os usuários solicitem produtos diretamente do catálogo do fornecedor em algumas entidades legais, mas não em outras, você pode usar **Impedir acesso** ou **Permitir acesso** para cada entidade legal onde deseja que o catálogo esteja ou não disponível.
5. No campo **Expiração padrão (dias)**, insira o número de dias que uma cotação recebida do catálogo externo é válida e pode ser usada para comprar do fornecedor externo. Quando uma cotação é criada e recuperada no site do catálogo externo do fornecedor, ela é válida a partir da data atual do sistema e permanece válida pelo número de dias especificado nesse campo.
6. Clique no botão **Adicionar** para começar a mapear as categorias de compras no catálogo externo. Então, na lista Nome da categoria, selecione uma categoria. A lista de categorias é um super conjunto de categorias de compras no qual o fornecedor foi mapeado em todas as entidades legais que estão configuradas para o fornecedor.

    > [!NOTE]
    > As políticas de compras são usadas para permitir ou restringir o acesso a categorias para a entidade legal de compra ou a unidade operacional de recebimento. O punchout para um catálogo externo exige que o acesso seja permitido a pelo menos uma das categorias de compras que são mapeadas para o catálogo.

7. Configure a mensagem de solicitação de configuração cXML que será enviada ao fornecedor. O formato de mensagem gerado automaticamente é o modelo mínimo que é necessário para iniciar uma sessão. Preencha os valores das etiquetas.

A qualquer momento, você pode recarregar o modelo de mensagem gerado pelo sistema, clicando em **Restaurar o formato da mensagem**. 
Observe que, se você restaurar o formato da mensagem, a mensagem atual será substituída pelo formato de mensagem gerado automaticamente, que possui etiquetas vazias

### <a name="cxml-setup-message"></a>Mensagem de configuração de cXML
Abaixo, você pode encontrar uma descrição das tags incluídas no modelo:

| Campo | Descrição | 
|---------|---------|
|< Header >< From >< Credential domain=”” >|O domínio da empresa do comprador.|
|< Header >< From >< Credential>< Identity >< /Identity > | A identidade da empresa do comprador.|
|< Header >< To >< Credential domain=”” > | O domínio da empresa do fornecedor.|
|< Header >< To >< Credential>< Identity >< /Identity> | A identidade da empresa do fornecedor.|
|< Header >< Sender >< Credential domain=”” > | O domínio da empresa do comprador.|
|< Header >< Sender >< Credential >< Identity >< /Identity> | A identidade da empresa do comprador.|
|< Header >< Sender >< Credential >< SharedSecret >< /SharedSecret >|O segredo compartilhado da empresa do comprador.|
|< Request deploymentMode=”” >|O teste ou a implementação de produção.|
|< Request >< PunchOutSetupRequest >< SupplierSetup >< URL >< /URL>|O URL da empresa de punchout do fornecedor.|

### <a name="extrinsic-elements"></a>Elementos extrínsecos

Um elemento extrínseco é uma informação adicional, como nome de usuário que se baseie em um usuário que forçou sua saída. O elemento extrínseco é definido quando o punchout ocorre e pode ser enviado na mensagem de configuração da solicitação.
O fornecedor pode ter um requerimento para receber um elemento no extrínseco de configuração. Nesse caso, você deve adicionar o elemento extrínseco à lista de elementos extrínsecos na seção **Formato de mensagem** da página **Catálogo externo**. Especifique um nome para o elemento extrínseco que o fornecedor pode reconhecer e mapeie-o para um valor. As opções para valores são: nome do usuário, e-mail do usuário ou valor aleatório.
Para obter mais informações sobre o protocolo cXML, consulte o [site do cXML.org](http://cxml.org/).

## <a name="post-back-message"></a>Mensagem pós-datada
A mensagem pós-datada é a mensagem que é recebida do fornecedor quando o usuário verifica o site externo e retorna para Finance and Operations. As mensagens pós-datadas não podem ser configuradas. As mensagens são baseadas na definição do protocolo de cXML. Aqui está a informação que pode ser parte da mensagem pós-datada da mensagem que é recebida em uma linha de requisição:

| Mensagem recebida do fornecedor | Copiado para a linha de requisição no Finance and Operations|
|------------------------------|----------------------------------------------------------|
|< ItemIn quantity=”” > |Quantidade|
|< ItemIn>< ItemID >< SupplierPartID >< /SupplierPartID >|ID de item externo|
|< ItemDetail>< UnitPrice >< Money currency=”” >| Moeda|
|< ItemDetail >< UnitPrice >< Money >< /Money >| Preço unitário|
|< ItemDetail >< Description ShortName=”” >|Nome do produto|
|< ItemDetail >< Description >< /Description >|Incluído na descrição do item; nome do produto se ShortName não for especificado.|
|< ItemDetail >< UnitOfMeasure >< /UnitOfMeasure >|Unidade|
|< ItemDetail >< Classification >< /Classification >|Incluído na descrição do item|
|< ItemDetail >< Classification domain=”” >|Incluído na descrição do item|

## <a name="delete-an-external-catalog"></a>Excluir um catálogo externo
Exclua um catálogo externo com a ação de exclusão na página.

Se um produto do catálogo de fornecedor externo for solicitado, o catálogo de fornecedor externo não poderá ser excluído. Em vez disso, o status do catálogo de fornecedor externo é definido como inativo. Se você deseja remover o acesso ao site de catálogo do fornecedor externo, mas não excluí-lo, altere o status do catálogo externo para inativo.

