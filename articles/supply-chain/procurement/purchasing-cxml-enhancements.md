---
title: Aprimoramentos ao cXML de compra
description: O recurso Aprimoramentos ao cXML de compra se baseia na funcionalidade de catálogo externo existente, PunchOut, que é usada para requisições de compra.
author: dasani-madipalli
manager: tfehr
ms.date: 08/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-08-03
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: cd0435fd89050311ecd4f24400d5830cbcf8fdfd
ms.sourcegitcommit: b281ac04157f6ccbd159fc89f58910b430a3b6a9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/21/2020
ms.locfileid: "3826916"
---
# <a name="purchasing-cxml-enhancements"></a>Aprimoramentos ao cXML de compra

[!include [banner](../includes/banner.md)]

O recurso _Aprimoramentos ao cXML de compra_ se baseia na [funcionalidade de catálogo externo existente](set-up-external-catalog-for-punchout.md) que é usada para requisições de compra. Essa funcionalidade existente é conhecida como _PunchOut_. Embora uma ordem de compra não tenha que se originar de uma requisição de compra, deve haver uma conexão entre o fornecedor em uma ordem de compra e os parâmetros que são usados para enviar o documento da ordem de compra.

## <a name="turn-on-the-purchasing-cxml-enhancements-feature"></a>Ativar o recurso Aprimoramentos ao cXML de compra

Para ativar o recurso, abra a página **[Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** e procure o recurso chamado *Aprimoramentos ao cXML de compra*. Selecione o recurso e, em seguida, **Habilitar agora** para ativá-lo.

Depois de ativar o recurso, você deve definir as configurações nas três áreas a seguir:

- **[Parâmetros cXML](#cxml-parameters)** – Use essas configurações para definir alguns parâmetros globais da funcionalidade de envio de ordens de compra.
- **[Configuração do fornecedor](#vendor-setup)** – Se a XML (eXtensible Markup Language) deve ser usada por padrão em todas as novas ordens de compra que são criadas para qualquer fornecedor, defina a opção **Enviar ordem de compra via cXML** como _Sim_ desse fornecedor.
- **[Catálogos externos](#external-catalog-setup)** – Use as novas configurações **Propriedades da ordem** para definir o formato do documento da ordem de compra e como ele é enviado.

A ilustração a seguir resume essa configuração.

![Áreas para configurar recursos de cXML](media/cxml-settings-areas.png "Áreas para configurar recursos de cXML")

Além disso, você deve configurar o [Trabalho em lotes de solicitação de ordem de compra](#po-batch). Esse trabalho em lotes é usado para enviar as ordens de compra confirmados.

## <a name="set-up-global-cxml-parameters"></a><a name="cxml-parameters"></a>Configurar parâmetros cXML globais

Use a página **Parâmetros cXML** para fazer algumas configurações globais que se aplicam à funcionalidade de envio de ordens de compra.

![Página Parâmetros cXML](media/cxml-parameters.png "Página Parâmetros cXML")

Vá para **Compras e fornecimento \> Configuração \> Gerenciamento de cXML \> Parâmetros cXML** e defina os seguintes parâmetros:

- **Modo de teste cXML** – Este parâmetro global afeta a maneira como as ordens de compra são fisicamente enviadas do trabalho em lotes. Selecione um dos seguintes valores:

    - **Teste** – Nesse modo, o trabalho em lotes pode estar em execução e o documento XML para a mensagem é gerado, mas não é enviado. Em vez disso, ele é salvo na solicitação de ordem de compra para fins de revisão. Esse modo é útil quando você está em uma implementação inicial e deseja ver como os dados são inseridos na mensagem de cXML. Você também pode gerar mensagens de amostra que podem ser enviadas aos fornecedores para validação inicial.
    - **Ativo** – Neste modo, o recurso usa as [configurações do catálogo externo](#external-catalog-setup) para transmitir fisicamente cada documento ao fornecedor.

- **Enviar atualizações de solicitação de compra** – Defina esta opção como *Sim* para enviar uma mensagem de atualização para ordens de compra. Defina-a como *Não* para evitar que a mensagem seja enviada. A maioria dos fornecedores prefere não receber mensagens de atualização. Em vez disso, os fornecedores exigem que os clientes os contatem por telefone ou e-mail se uma ordem de compra tiver que ser alterada. Esse parâmetro é um parâmetro global e nenhuma substituição pode ser especificada no catálogo externo de cada fornecedor. Uma ordem de compra será marcada como atualizada se você lançar uma segunda confirmação em uma ordem de compra, mas a primeira confirmação já foi enviada e reconhecida pelo fornecedor. Se houver uma segunda confirmação, mas a primeira não tiver sido enviada, a segunda confirmação será tratada como um novo documento. É possível confirmar uma ordem de compra quantas vezes quiser até que uma confirmação seja enviada. A próxima confirmação será tratada como uma mensagem de atualização.
- **Enviar exclusão de solicitação de compra** – Defina esta opção como *Sim* para enviar uma mensagem de exclusão para ordens de compra. Defina-a como *Não* para evitar que a mensagem seja enviada. A maioria dos fornecedores prefere não receber mensagens de exclusão. Em vez disso, os fornecedores exigem que os clientes os contatem por telefone ou e-mail se uma ordem de compra foi enviada por engano. Esse parâmetro é um parâmetro global e nenhuma substituição pode ser especificada no catálogo externo de cada fornecedor. Uma ordem de compra será marcada como excluída se você cancelá-la no Supply Chain Management.
- **Arquivar arquivo** – Especifique o caminho do arquivo onde deseja exportar e salvar documentos cXML arquivados. O caminho é usado quando você executa a função de eliminação da página **Solicitação de ordem de compra**.
- **Máximo de caracteres para linha de rua** – Insira o número máximo de caracteres que podem ser usados no campo da rua para endereços no documento cXML. Esse parâmetro global afeta todos os fornecedores, a menos que uma substituição seja especificada nas propriedades do catálogo externo.

## <a name="set-up-vendor-purchase-orders-to-use-cxml"></a><a name="vendor-setup"></a>Configurar as ordens de compra do fornecedor para usar a cXML

Sempre que você confirma uma ordem de compra em que a opção **Enviar ordem de compra via cXML** está definida como _Sim_, o sistema gera automaticamente a mensagem de cXML e a entrega ao fornecedor associado a essa ordem de compra. Existem duas maneiras de controlar essa opção para suas ordens de compra:

- Para configurar um fornecedor para que ele use a cXML automaticamente em todas as novas ordens de compra criadas por meio de uma requisição, acesse **Compras e fornecimento \> Fornecedores \> Todos os fornecedores** e selecione ou crie um fornecedor para abrir sua página de detalhes. Depois, na Guia Rápida **Padrões da ordem de compra**, defina a opção **Enviar ordem de compra via cXML** como _Sim_. Se a cXML também tiver que ser usada automaticamente em novas ordens de compra que são **não** criadas por meio de uma requisição, você também deve definir a propriedade da pedido **ENABLEMANUALPO** como _True_ para o catálogo externo relacionado, conforme descrito na seção [Definir as propriedades da ordem](#set-order-properties) posteriormente neste tópico.
- Para ordens de compra individuais, vá para **Compras e fornecimento \> Ordens de compra \> Todas as ordens de compra** e selecione ou crie uma ordem de compra para abrir sua página de detalhes. Alterne para a exibição **Cabeçalho** e, na Guia Rápida **Configuração**, defina a opção **Enviar ordem de compra via cXML** conforme necessário.

![Configurações padrão para ordens de compra do fornecedor](media/cxml-order-defaults.png "Configurações padrão para ordens de compra do fornecedor")

## <a name="set-up-an-external-catalog-to-use-cxml"></a><a name="external-catalog-setup"></a>Configurar um catálogo externo para usar cXML

Na página **Catálogos externos**, para cada um de seus catálogos, você pode configurar a funcionalidade PunchOut e a funcionalidade para enviar ordens de compra. Para encontrar as configurações relevantes, vá para **Compras e fornecimento \> Catálogos \> Catálogos externos**. Comece [configurando cada catálogo como de costume](set-up-external-catalog-for-punchout.md). Esse processo inclui atribuir um fornecedor, selecionar as categorias que o fornecedor tem permissão para fornecer e ativar o catálogo. Em seguida, defina as configurações adicionais descritas nesta seção.

> [!NOTE]
> Quando você confirma uma ordem de compra que pode ser enviada via cXML, o sistema procura o fornecedor associado à ordem de compra e, em seguida, encontra o primeiro catálogo externo ativo associado a esse fornecedor. Depois, o sistema usa as configurações desse catálogo externo para enviar a ordem de compra. Se vários catálogos externos forem configurados, o sistema usará apenas o primeiro catálogo externo que encontrar, com base no fornecedor na ordem de compra. Portanto, recomendamos que você crie apenas um catálogo externo para cada fornecedor.

![Configurações de catálogo externo](media/cxml-supplier-catalog.png "Configurações de catálogo externo")

### <a name="set-the-punchout-protocol-type"></a>Definir o tipo de protocolo PunchOut

Na Guia Rápida **Geral** da página **Catálogos externos**, defina o campo **Tipo de protocolo PunchOut** como _cXML_. Essa opção será a única opção disponível, a menos que um parceiro tenha estendido a funcionalidade e forneça uma opção adicional na extensão.

Se você também estiver usando o catálogo para PunchOut, você também deve [configurar o formato da mensagem](set-up-external-catalog-for-punchout.md). O formato da mensagem é usado para estabelecer a conexão com o fornecedor na transação PunchOut da requisição. Quando uma ordem de compra é enviada, as propriedades da ordem serão usadas para estabelecer a conexão com um fornecedor.

### <a name="set-the-order-properties"></a><a name="set-order-properties"></a>Definir as propriedades da ordem

O recurso _Aprimoramentos ao cXML de compra_ adiciona uma nova Guia Rápida **Propriedades da ordem** para catálogos externos. Essa Guia Rápida fornece uma grade onde você pode definir as propriedades da ordem. Também fornece uma barra de ferramentas. Essa barra de ferramentas contém os três botões a seguir que você pode usar para gerenciar as propriedades da ordem:

- **Propriedades padrão** – Ao configurar um novo catálogo, selecione este botão para adicionar à grade uma coleção predefinida de propriedades comumente usadas.
- **Novo** – Adicione uma nova propriedade à grade.
- **Excluir** – Exclua a propriedade atualmente selecionada da grade. Se você acidentalmente excluir uma propriedade padrão, selecione **Propriedades padrão** para restaurar todas as propriedades ausentes.

Sempre que adicionar uma ou mais propriedades à grade, use a coluna certa para especificar um valor para cada uma.

Use as propriedades padrão da seguinte forma:

- **BUYER\_COOKIE** – Este campo de rastreamento pode ser usado para indicar informações específicas para sua empresa. A menos que você tenha um contrato com o fornecedor sobre como essa propriedade é usada, não haverá muito sentido em enviar uma ordem de compra. Portanto, você deve defini-lo com um valor simples.
- **DELIVERTO** – Quando o endereço de remessa é inserido no documento da ordem de compra, o campo **Informações de atenção** é usado para definir o campo **DeliverTo** na mensagem XML. Se você exigir que esse valor seja um nome de solicitante e definir o campo do solicitante no cabeçalho da ordem de compra, insira o valor _REQUESTER_ dessa propriedade para que o nome do solicitante seja inserido no campo **DeliverTo** no XML. Nesse caso, o endereço de email principal e o número de telefone usados serão do solicitante e não do autor da ordem.
- **DEPLOYMENTMODE** – Defina esta propriedade conforme exigido pelo fornecedor. Em geral, os valores são _PRODUCTION_ ou _TEST_. Defina o valor com base em sua comunicação com o fornecedor. Geralmente, ele deve corresponder ao sistema pretendido por trás do valor **ORDERCHECKURL** que o fornecedor indica como um sistema de teste ou produção.
- **FIXEDBILLADDRESSID** – Quando o campo **addressID** na mensagem XML é definido, ele seleciona o local que está especificado no endereço. Se o valor da ID que você comunicou ao fornecedor for diferente do valor no local do endereço por algum motivo, você pode forçar uma substituição especificando o valor aqui. A suposição é que você usará apenas um endereço com o fornecedor e que o endereço está configurado no sistema do fornecedor. O endereço de cobrança é o endereço principal da fatura especificado para a entidade legal no Supply Chain Management.
- **FIXEDSHIPADDRESSID** – Quando o campo **addressID** na mensagem XML é definido, ele seleciona o local que está especificado no endereço. Se o valor da ID que você comunicou ao fornecedor for diferente do valor no local do endereço por algum motivo, você pode forçar uma substituição especificando o valor aqui. A suposição é que você usará apenas um endereço com o fornecedor e que o endereço está configurado no sistema do fornecedor. O endereço de remessa é o endereço especificado no cabeçalho da ordem de compra. A maioria dos fornecedores aceita apenas endereços de cabeçalho, não endereços de linha. Embora existam campos para endereços de linha no XML, eles serão configurados para o endereço do cabeçalho.
- **FROM\_DOMAIN** – Insira o valor que é usado para enviar documentos da ordem de compra. Esse valor é fornecido pelo seu fornecedor.
- **FROM\_IDENTITY** – Insira o valor que é usado para enviar documentos da ordem de compra. Esse valor é fornecido pelo seu fornecedor.
- **ORDERCHECKURL** – Insira a URL à qual serão transmitidos os documentos da ordem de compra. Essa URL começa com `https://` e é fornecida pelo seu fornecedor.
- **PAYLOAD\_ID** – Insira um valor de prefixo para a ID de payload, conforme necessário, para os processos de negócios que estão em vigor para o fornecedor atual.
- **SENDER\_DOMAIN** – Insira o valor que é usado para enviar documentos da ordem de compra. Esse valor é fornecido pelo seu fornecedor.
- **SENDER\_IDENTITY** – Insira o valor que é usado para enviar documentos da ordem de compra. Esse valor é fornecido pelo seu fornecedor.
- **SHARED\_SECRET** – Insira o valor que é usado para enviar documentos da ordem de compra. Esse valor é fornecido pelo seu fornecedor.
- **STREETLENGTH** – Insira um número que represente o número máximo de caracteres que o vendedor aceitará como nome de rua. Se um valor for inserido aqui, ele substituirá o valor que é especificado na página **Parâmetros cXML**. O sistema removerá as quebras de linha e espaços para tentar ajustar o endereço padrão no Supply Chain Management ao número de caracteres especificado aqui. Quaisquer caracteres adicionais serão truncados.
- **TO\_DOMAIN** – Insira o valor que é usado para enviar documentos da ordem de compra. Esse valor é fornecido pelo seu fornecedor.
- **TO\_IDENTITY** – Insira o valor que é usado para enviar documentos da ordem de compra. Esse valor é fornecido pelo seu fornecedor.
- **USERAGENT** – Insira um valor para identificar o sistema que você está usando. Por exemplo, insira _Dynamics 365 Supply Chain Management_.
- **VERSION** – Insira um número de versão de cXML, se o fornecedor solicitar essas informações. A versão padrão é *1.2.008*. Essa versão é estável e aceita pela maioria dos fornecedores.
- **RESPONSETEXT** – Insira qualquer texto personalizado que você espera que o fornecedor retorne na mensagem de resposta de cXML após o envio da ordem. Assim, o sistema pode marcar a mensagem como _Confirmada_. Se a resposta não corresponder ao texto padrão ou ao texto do cliente inserido aqui, a solicitação será marcada como _Erro_.
- **RESPONSETEXTSUB** – Defina esta propriedade como _TRUE_ se desejar pesquisar o texto de resposta do fornecedor para os valores que são especificados no campo **RESPONSETEXT**. Por exemplo, o fornecedor pode retornar uma longa cadeia de caracteres que inclui "OK" na resposta. Nesse caso, você pode inserir _OK_ no campo **RESPONSETEXT** e definir **RESPONSETESTSUB** como _TRUE_ para pesquisar "OK" em qualquer lugar da resposta. A ordem pode então ser definida como _Confirmada_.
- **CONTENTTYPE** – Em uma configuração de catálogo típica, você não precisa definir essa propriedade. Se você receber um erro de servidor 500 do sistema de um fornecedor ao enviar uma ordem de compra, poderá fazer o teste definindo essa propriedade como _FALSE_. Esse valor mudará uma configuração na solicitação Web e pode permitir que a mensagem seja enviada para algumas plataformas.
- **ENABLEHEADERS** – Defina esta propriedade como _TRUE_ para enviar cabeçalhos juntamente com a ordem de compra. Você deve definir essa propriedade apenas se o fornecedor exigir. Se você configurar essa propriedade como _TRUE_, inclua propriedades personalizadas extras que são baseadas nos nomes que o fornecedor fornece e prefixe-as com _H\__. Exemplos típicos incluem **H\_USERID**, **H\_PASSWORD**, **H\_RECEIVERID** e **H\_ACTIONREQUEST**. As seguintes propriedades personalizadas estão incluídas nas propriedades padrão:

    - **H\_USERID** – Se o parceiro comercial exigir que você envie uma ID de usuário como parte da URL para enviar uma ordem de compra, insira o valor aqui.
    - **H\_PASSWORD** – Se o parceiro comercial exigir que você envie uma senha como parte da URL para enviar uma ordem de compra, insira o valor aqui.

- **ENABLEMANUALPO** – Se esta propriedade for definida como _TRUE_, quando os usuários criam ordens de compra manualmente (ou seja, quando não começam a partir de uma requisição), essas ordens de compra herdam a configuração da opção **Enviar ordem de compra via cXML** do fornecedor. Se essa propriedade não for definida, ou se for definida como _FALSE_, a opção **Enviar ordem de compra via cXML** não será definida no cabeçalho da ordem de compra para ordens criadas manualmente. Para ordens de compra criadas a partir de uma requisição, a configuração da opção **Enviar ordem de compra via cXML** é sempre herdada do fornecedor, independentemente da configuração dessa propriedade. Para obter mais informações, consulte a seção [Configurar as ordens de compra do fornecedor para usar a cXML](#vendor-setup) anteriormente neste tópico.
- **PUNCHOUTPOONLY** – Se esta propriedade for definida como _TRUE_, apenas as linhas de requisição de compra criadas a partir do processo PunchOut definirão a opção **Enviar ordem de compra via cXML** no cabeçalho da ordem de compra. Além disso, o tipo de linha de requisição de compra de todas as linhas da ordem deve ser _Item de catálogo externo_. Caso contrário, a ordem de compra cXML não pode ser criada.
- **PUNCHOUTSHIPTO** – Se esta propriedade for definida como _TRUE_, o endereço padrão da entidade legal será adicionado à mensagem de solicitação de configuração PunchOut quando o usuário abrir um catálogo externo. Esse endereço é adicionado como o endereço **ShipTo**. Os fornecedores usarão o endereço **ShipTo** para mostrar os preços com base na localização da empresa.
- **TRACEPUNCHOUT** – Defina esta propriedade como _TRUE_ se você receber uma mensagem de erro ao tentar navegar para um catálogo externo da requisição. As informações de rastreamento serão preenchidas para as mensagens **PunchOutSetupRequest** e **PunchOutResponse** que são enviadas entre o Supply Chain Management e o site do fornecedor. Você pode ver essas informações na página **Log de mensagens do carrinho cXML**, que pode ser aberta na página **Configuração de catálogo externo** para o catálogo do fornecedor com o qual você está tendo problemas. Você deve definir essa propriedade como _TRUE_ somente se estiver solucionando problemas, porque isso cria uma grande sobrecarga de desempenho no banco de dados para cada PunchOut. Para obter mais informações, consulte a seção [Exibir o log de mensagens do carrinho cXML para o catálogo externo PunchOut](#message-log) posteriormente neste tópico.
- **REPLACENEWLINE** – Defina esta propriedade como _TRUE_ se estiver tendo um problema porque o sistema de um fornecedor está enviando uma mensagem **PunchOutResponse** que inclui caracteres de nova linha (\\n). Esse problema pode ocorrer se as mensagens do fornecedor forem analisadas por meio de middleware ou um hub de compras. Se você estiver tendo problemas com a configuração de um novo fornecedor, defina a propriedade **TRACEPUNCHOUT** como _TRUE_ para exibir a mensagem **PunchOutResponse** e determinar se as tags XML estão divididas por caracteres de nova linha.
- **POCOMMENTS** – Defina esta propriedade como _TRUE_ se desejar que o documento cXML inclua notas anexadas à ordem de compra no Supply Chain Management. O texto do anexo é incluído nos comentários do cabeçalho na mensagem da ordem de compra. Para obter mais informações sobre como o sistema seleciona e processa esses anexos, consulte a seção [Anexar notas a uma ordem de compra](#attach-po-notes) posteriormente neste tópico.
- **VENDCOMMENTS** – Defina esta propriedade como _TRUE_ se desejar que o documento cXML inclua notas anexadas à ordem de compra no Supply Chain Management. O texto do anexo é incluído nos comentários do cabeçalho na mensagem da ordem de compra. Para obter mais informações sobre como o sistema seleciona e processa esses anexos, consulte a seção [Anexar notas a uma ordem de compra](#attach-po-notes).
- **CLEANAMP** – Defina esta propriedade como _TRUE_ se você receber uma mensagem de erro ao tentar fazer um PunchOut para um fornecedor e a URL de retorno do fornecedor incluir e comercial codificado incorretamente (\&).
- **PUNCHOUTTZ** – Defina esta propriedade como _TRUE_ se o fornecedor com o qual você está trabalhando usa o padrão 8601 da Organização Internacional de Normalização (International Organization for Standardization, ISO) para fazer uma validação específica da data/hora da mensagem de solicitação PunchOut. O Supply Chain Management usa a data do Tempo Universal Coordenado (UTC) na mensagem **PunchOutSetupRequest**. Portanto, ao definir esta propriedade como _TRUE_, *+00:00* é adicionado ao formato de data/hora.
- **WMSADDRESSID** – Defina esta propriedade como _TRUE_ para usar o número do depósito no cabeçalho da ordem de compra como o valor **addressID** no endereço **ShipTo** para a solicitação de ordem de compra que é enviada ao fornecedor. Se você definir um valor para a propriedade **FIXEDSHIPADDRESSID**, esse valor terá prioridade sobre esse valor. Portanto, você deve usar uma propriedade ou outra para definir o valor **addressID** no endereço **ShipTo** para o documento.
- **PUNCHOUTSHIPTOUSER** – Esta propriedade trabalha em conjunto com a propriedade **PUNCHOUTSHIPTO**. Se **PUNCHOUTSHIPTO** for definido como _TRUE_, o endereço da entidade legal será selecionado. Se **PUNCHOUTSHIPTOUSER** for definido como _TRUE_, o endereço principal do usuário PunchOut será usado em vez do endereço da entidade legal.

### <a name="activate-the-external-catalog"></a>Ativar o catálogo externo

Quando você terminar de configurar todas as propriedades e definir outras configurações para seu catálogo externo, volte para a Guia Rápida **Geral** da página **Catálogos externos** e defina a opção **Ativo** como *Sim*.

### <a name="attach-notes-to-a-purchase-order"></a><a name="attach-po-notes"></a>Anexar notas a uma ordem de compra

Como foi mencionado na seção [Definir as propriedades da ordem](#set-order-properties), se desejar que seu cXML entregue inclua texto de notas anexadas à ordem de compra relevante e/ou registros do fornecedor, você pode definir a propriedade **POCOMMENTS** e/ou **VENDCOMMENTS** como _TRUE_ na configuração de catálogo externo. Esta seção fornece mais detalhes sobre como o sistema seleciona e processa esses anexos, se você usá-los.

Para definir os tipos de notas que o sistema procurará, vá para **Compras e fornecimento \> Configuração \> Formulários \> A partir da configuração**. Em seguida, na guia **Ordem de compra**, defina o campo **Incluir documentos do tipo** para o tipo de nota que deseja incluir. Somente notas de texto serão incluídas, não anexos de documentos.

![Página de configuração de formulários](media/cxml-form-setup.png "Página de configuração de formulários")

Os anexos serão incluídos em uma ordem de compra apenas se o campo **Tipo** for definido com o valor que você selecionar no campo **Incluir documentos do tipo** e se o campo **Restrição** for definido como _Externo_. Para criar, exibir ou editar os anexos de uma ordem de compra, vá para **Compras e fornecimento \> Todas as ordens de compra**, selecione ou crie uma ordem de compra e selecione o botão **Anexos** (símbolo de clipe de papel) no canto superior direito.

![Nota anexada configurada para ser enviada a um fornecedor](media/cxml-note-to-vendor.png "Nota anexada configurada para ser enviada a um fornecedor")

## <a name="view-the-cxml-cart-message-log-for-external-catalog-punchout"></a><a name="message-log"></a>Exibir o log de mensagens do carrinho cXML para o catálogo externo PunchOut

Quando você define o campo **Tipo de protocolo PunchOut** como _cXML_ para um catálogo externo, o sistema captura um log de mensagens de carrinho que retornam dos fornecedores. Esse registro pode ser usado para solução de problemas e outros propósitos de dados.

Para abrir o log de um catálogo externo, selecione o catálogo relevante e, em seguida, no Painel de ações, selecione **Log de mensagens do carrinho cXML**. A página **Log de mensagens do carrinho cXML** mostra uma lista dos carrinhos que foram devolvidos, o XML relacionado a esses carrinhos e as linhas que foram criadas na requisição de compra relacionada.

![Página Log de mensagens do carrinho cXML](media/cxml-cart-message-log.png "Página Log de mensagens do carrinho cXML")

## <a name="set-the-extrinsic-elements-for-external-catalog-punchout"></a>Definir os elementos extrínsecos para o catálogo externo PunchOut

Ao definir o campo **Tipo de protocolo PunchOut** como *cXML* para um catálogo externo, você pode adicionar elementos extrínsecos personalizados que serão inseridos no local correto na mensagem XML de solicitação.

Para adicionar elementos extrínsecos a um catálogo externo, siga as etapas a seguir.

1. Vá para **Compras e fornecimento \> Catálogos \> Catálogos externos**.
1. Selecione o catálogo relevante.
1. Na Guia Rápida **Formato da mensagem**, na seção **Extrínsecos**, selecione **Adicionar** para adicionar uma linha à grade para cada elemento extrínseco que deseja incluir. Em cada linha, defina os seguintes campos:

    - **Nome** – Insira um nome do elemento. Este valor se tornará o valor do atributo **nome** para o elemento XML **Extrínseco** que é criado para cada linha. Em geral, você trabalhará com seu fornecedor para chegar a um acordo sobre o nome de cada elemento extrínseco.
    - **Valor** – Selecione um valor para o elemento. Esse valor se tornará o valor do elemento XML que é criado por cada linha. Os valores a seguir estão disponíveis:

        - **Nome do usuário** – Use o nome do usuário que está fazendo o PunchOut. Este nome é o nome de entrada para Supply Chain Management.
        - **Email do usuário** – Use o endereço de email do usuário que está fazendo o PunchOut. Esse endereço é o endereço que o usuário configurou na guia **Conta** da página **Opções do usuário**.
        - **Valor aleatório** – Use um valor aleatório exclusivo.
        - **Nome completo do usuário** – Use o nome completo da pessoa de contato associada ao usuário que está acessando o catálogo externo.
        - **Nome** – Use o nome da pessoa de contato associada ao usuário que está acessando o catálogo externo.
        - **Sobrenome** – Use o sobrenome da pessoa de contato associada ao usuário que está acessando o catálogo externo.
        - **Número de telefone** – Use o número de telefone principal da pessoa de contato associada ao usuário que está acessando o catálogo externo.

![Configurações de elemento extrínseco](media/cxml-extrinsics.png "Configurações de elemento extrínseco")

O usuário ou administrador não verá os elementos extrínsecos, porque eles não são adicionados até que o usuário execute um PunchOut. Eles serão inseridos automaticamente entre os elementos **BuyerCookie** e **BrowserFromPost** na mensagem de solicitação de configuração cXML. Portanto, você não precisa defini-los manualmente no XML ao configurar o catálogo externo.

![Elementos extrínsecos adicionados ao XML](media/cxml-extrinsics-xml.png "Elementos extrínsecos adicionados ao XML")

## <a name="create-and-process-a-purchase-order"></a><a name="create-po"></a>Criar e processar uma ordem de compra

Quando você cria uma ordem de compra para um fornecedor, ela herda a configuração da opção **Enviar ordem de compra via cXML** desse fornecedor. Contudo, a configuração permanece disponível na Guia Rápida **Configuração** na exibição **Cabeçalho** da ordem de compra para que você possa alterá-la posteriormente, conforme necessário.

![Ordem de compra definida para usar cXML](media/cxml-purchase-order.png "Ordem de compra definida para usar cXML")

Ao criar uma ordem de compra a partir de uma requisição de compra oriunda de um fluxo PunchOut, todos os detalhes da linha necessários serão preenchidos. Depois, é possível adicionar manualmente as linhas da ordem de compra ou copiá-las de outras ordens de compra. Certifique-se de definir todos os campos obrigatórios. Esses campos obrigatórios incluem o número de referência externa, que é o número do fornecedor que será usado na mensagem cXML.

![Exemplo de um número de referência externo](media/cxml-line-details.png "Exemplo de um número de referência externo")

Quando terminar de preencher todos os detalhes da ordem de compra, não deixe de confirmá-la. Nenhuma mensagem é enviada a menos que a ordem de compra seja confirmada. No Painel de Ações, na guia **Compra**, no grupo **Ações**, selecione **Confirmar** para confirmar a ordem de compra. 

Após a confirmação da ordem de compra, você pode exibir o status da confirmação por meio dos diários **Confirmações de ordem de compra**. No Painel de Ação, na guia **Compra**, no grupo **Diários**, selecione **Confirmações de ordem de compra**.

Cada ordem de compra pode ter várias confirmações. Cada confirmação é marcada com um número incremental. Na ilustração a seguir, a ordem de compra é *00000275* e a confirmação é *00000275-1*. Essa numeração reflete a funcionalidade padrão do Supply Chain Management, em que as alterações em uma ordem de compra e, portanto, o tipo de mensagem cXML que deve ser enviada ao fornecedor, são identificadas com base na confirmação. Como mostra a ilustração, a página **Confirmações de ordem de compra** também inclui os campos **Status de envio da ordem** e **Status do fornecedor de solicitação de ordem**. Para obter mais informações sobre os vários valores de status que você pode ver nesta página, consulte a seção [Monitorar solicitações de ordem de compra](#monitor-po-requests) posteriormente neste tópico.

![Página Confirmações de ordem de compra](media/cxml-po-confirmations.png "Página Confirmações de ordem de compra")

Para exibir mais informações sobre o documento, selecione **Solicitação de ordem de compra** acima da grade.

A página **Solicitação de ordem de compra** inclui duas grades. A grade na parte superior da página possui um registro para cada ordem de compra marcada para envio. A grade na guia **Histórico de solicitações de ordem de compra** na parte inferior da página pode ter vários registros para a ordem de compra selecionada, para indicar o status de cada confirmação. A ilustração a seguir mostra a ordem de compra 00000275 na grade superior e o documento 00000275-1 na grade da guia **Histórico de solicitações de ordem de compra**.

![Página Solicitação de ordem de compra](media/cxml-po-request.png "Página Solicitação de ordem de compra")

Se o trabalho em lotes estiver configurado e em execução, o documento será enviado. Você pode exibir a mudança de status após o envio do documento. Na ilustração a seguir, o campo **Status de envio da ordem** é definido como _Enviado_. O campo **Status do fornecedor de solicitação de ordem** é definido como _Confirmado_ para indicar que o fornecedor recebeu o documento e foi capaz de lê-lo e armazená-lo em seu sistema. A grade na guia **Histórico de solicitações de ordem de compra** mostra a hora em que o documento foi enviado. Para obter mais informações sobre os vários valores de status que você pode ver nesta página, consulte a seção [Monitorar solicitações de ordem de compra](#monitor-po-requests).

![Mensagens de status na página Solicitação de ordem de compra](media/cxml-po-request-2.png "Mensagens de status na página Solicitação de ordem de compra")

## <a name="schedule-the-purchase-order-request-batch-job"></a><a name="po-batch"></a>Agendar o trabalho em lotes de solicitação de ordem de compra

Para ativar o trabalho em lotes para enviar solicitações de ordem de compra, acesse **Compras e fornecimento \> Configuração \> Gerenciamento de cXML \> Solicitação de ordem de compra** e, no Painel de Ações, na guia **Solicitação de ordem de compra**, no grupo **Lote**, selecione **Enviar trabalho** para abrir a caixa de diálogo **Preparação e envio da solicitação de compra**. É possível usar essa caixa de diálogo para configurar a recorrência, assim como você costuma fazer para trabalhos em lotes no Supply Chain Management. Selecione um intervalo, com base no volume da sua ordem. Embora você possa executar o trabalho em lotes a cada minuto, provavelmente é melhor enviar lotes durante o dia útil, com base nas janelas de recebimento de ordem que correspondem às programações de seus fornecedores.

Por exemplo, seu fornecedor tem uma política que determina que todas as ordens recebidas até 13h serão remetidas no mesmo dia. Nesse caso, talvez você precise executar o lote apenas algumas vezes durante a manhã para comunicar suas ordens. Depois, as ordens restantes serão enviadas no dia seguinte. Essa decisão é puramente uma decisão de negócios. Você pode analisá-la e definir seus parâmetros adequadamente.

O processo procurará documentos de solicitação de ordem de compra que tenham um status de *Aguardando*. Se você tiver uma ordem a ser enviada a um fornecedor imediatamente, selecione **Enviar trabalho** e defina a opção **Processamento em lotes** como *Não*.

## <a name="monitor-purchase-order-requests"></a><a name="monitor-po-requests"></a>Monitorar solicitações de ordem de compra

### <a name="view-the-status-of-a-purchase-order"></a>Exibir o status de uma ordem de compra

Quando as ordens que podem ser enviadas via cXML são confirmadas, elas passam para o status _Aguardando_. Como foi descrito na seção [Criar e processar uma ordem de compra](#create-po), você pode exibir o status da ordem de compra na página **Solicitação de ordem de compra**. Cada solicitação de ordem de compra pode ter um de vários status, dependendo de seus parâmetros e dados. Esta seção descreve os vários tipos de status e os valores que eles podem ter. Essas informações podem ajudá-la a gerenciar problemas e entender o status das ordens de compra.

![Status da ordem de compra na página Solicitação de ordem de compra](media/cxml-monitor-po-request.png "Status da ordem de compra na página Solicitação de ordem de compra")

A grade na parte superior da página **Solicitação de ordem de compra** pode mostrar os seguintes valores de status:

- **Status de envio da ordem** – Este campo pode ter um dos seguintes valores:

    - **Aguardando** – O documento está aguardando envio.
    - **Enviado** – O documento foi enviado.
    - **Interrompido** – O documento foi marcado como _Interrompido_ antes de ser enviado. (Para marcar um documento como _Interrompido_, selecione **Interromper** no Painel de Ações da página **Solicitação de compra**.)
    - **Arquivar** – O documento foi eliminado. (Para limpar um documento, selecione **Limpar** no Painel de Ações da página **Solicitação de compra**.)

- **Status do fornecedor de solicitação de ordem** – Este campo pode ter um dos seguintes valores:

    - **Aguardando** – O documento está aguardando envio.
    - **Confirmado** – O documento foi reconhecido como recebido pelo fornecedor. Você pode analisar a mensagem XML detalhada que é retornada do fornecedor selecionando a guia **Resposta XML** na parte inferior da página.
    - **Erro** – O documento foi enviado ao fornecedor, mas ocorreu um erro. Você pode revisar a mensagem de erro selecionando a guia **Resposta XML** na parte inferior da página.

A grade na guia **Histórico de solicitações de ordem de compra** na parte inferior da página **Solicitação de ordem de compra** pode mostrar os seguintes valores:

- **Tipo de solicitação de ordem** – Este campo pode ter um dos seguintes valores:

    - **Novo** – A linha é marcada como nova imediatamente após a confirmação da ordem de compra.
    - **Atualizar** – Se uma confirmação já foi enviada e confirmada pelo fornecedor, a próxima confirmação será marcada como _Atualizar_. As atualizações serão enviadas apenas se a opção **Enviar atualizações de solicitação de compra** for definida como *Sim* nos [parâmetros cXML globais](#cxml-parameters).
    - **Excluir** – Se já houver uma confirmação enviada e confirmada pelo fornecedor, mas a ordem de compra for cancelada, a confirmação que está aguardando será marcada como _Excluir_. As exclusões serão enviadas apenas se a opção **Enviar exclusão de solicitação de compra** for definida como *Sim* nos [parâmetros cXML globais](#cxml-parameters).

- **Hora da solicitação** – A hora em que a confirmação da ordem foi criada. Você pode comparar a hora da solicitação com o tempo do status da ordem para determinar o tempo entre a confirmação e o reconhecimento do fornecedor.
- **Status de envio da ordem** – Este campo é igual ao campo **Status de envio da ordem** na parte superior da página. Ele é repetido aqui para facilitar a exibição do status no nível de confirmação. Se o campo **Tipo de solicitação de ordem** for definido como *Novo* e a ordem de compra for reconfirmada antes do envio de uma confirmação, o campo **Status de envio da ordem** será definido como *Arquivo*.
- **Hora do status da ordem** – A hora em que o registro do histórico de ordens de compra foi atualizado pela última vez. (As atualizações incluem mudanças de status.)
- **Status do fornecedor de solicitação de ordem** – Este campo é igual ao campo **Status do fornecedor de solicitação de ordem** na parte superior da página. Ele é repetido aqui para facilitar a exibição do status no nível de confirmação.
- **Hora de reenvio** – A hora em que o registro foi reenviado.
- **Reenviar contagem** – O número de vezes que o registro foi reenviado. Um número alto indica várias falhas e, portanto, pode indicar um problema com a configuração de dados ou com a configuração de dados do fornecedor.

### <a name="view-the-xml-for-a-purchase-order-request-message"></a>Exibir o XML de uma mensagem de solicitação de ordem de compra

Para exibir o XML da mensagem de solicitação de ordem de compra, selecione a guia **Solicitar texto XML** na parte inferior da página **Solicitação de ordem de compra**. As informações nesta guia podem ser úteis durante o teste ou validação de erro. Para tornar as informações mais fáceis de ler, você pode exibi-las como uma mensagem formatada. Copie o conteúdo da guia em um arquivo de texto e exiba-o em um editor de XML.

![Guia Solicitar texto XML](media/cxml-request-xml-text.png "Guia Solicitar texto XML")

### <a name="view-the-details-of-the-vendor-response"></a>Exibir os detalhes da resposta do fornecedor

Para exibir o conteúdo de uma confirmação de fornecedor ou resposta de erro, selecione a guia **Resposta XML** na parte inferior da página **Solicitação de ordem de compra**.

![Guia Resposta XML](media/cxml-response-xml.png "Guia Resposta XML")

## <a name="additional-resources"></a>Recursos adicionais

- [​Configurar um catálogo externo para PunchOut e-procurement​](set-up-external-catalog-for-punchout.md)
- [​Uso de catálogos externos para PunchOut e-procurement](use-external-catalogs-for-punchout.md)
