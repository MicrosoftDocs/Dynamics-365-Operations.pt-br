---
title: Visão geral de pagamentos de omni-channel
description: Este tópico fornece uma visão geral de pagamentos de omni-channel no Dynamics 365 Commerce.
author: rubendel
manager: AnnBe
ms.date: 09/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: AX 8.1.3
ms.openlocfilehash: 6ecfd518298021e08cf73934b450d175cf699a46
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985852"
---
# <a name="omni-channel-payments-overview"></a>Visão geral de pagamentos de omni-channel

[!include [banner](../includes/banner.md)]

Este tópico fornece uma visão geral de pagamentos de omni-channel no Dynamics 365 Commerce. Ele inclui uma lista abrangente de cenários com suporte, informações sobre funcionalidade, configuração e solução de problemas e descrições de alguns problemas típicos.

## <a name="key-terms"></a>Condições principais

| Termo | Descrição |
|---|---|
| Token  | Uma sequência de dados que um processador de pagamento fornece como referência. Os tokens podem representar números de cartão de pagamento, autorizações de pagamento e capturas de pagamento anteriores. Os tokens são importantes porque ajudam a manter dados confidenciais fora do sistema de ponto de venda (PDV). Às vezes também são chamados de *referências*. |
| Token de cartão | Um token que um processador de pagamento fornece para armazenamento no sistema de PDV. Um token de cartão só pode ser usado pelo comerciante que o recebe. Os tokens de cartão às vezes também são chamados de *referências de cartões*. |
| Token de autorização (auth) | Uma ID exclusiva que um processo de pagamento fornece como parte da resposta que envia a um sistema de PDV depois que o sistema de PDV faz uma solicitação de autorização. Um token de autorização pode ser usado posteriormente se o processador for chamado para executar ações, como reverter ou anular a autorização. Entretanto, é mais usado para capturar fundos quando uma ordem é atendida ou uma transação é finalizada. Os tokens de autorização às vezes também são chamados de *referências de autorização*. |
| Token de captura | Uma referência que um processador de pagamento fornece a um sistema de PDV quando um pagamento é finalizado ou capturado. O token de captura pode ser usado para referenciar a captura de pagamento em operações subsequentes, como solicitações de reembolso. | 
| O cartão não está presente | Um termo que se refere a transações de pagamento em que um cartão físico não é apresentado. Por exemplo, essas transações podem ocorrer em cenários de comércio eletrônico ou call center. Para essas transações, as informações relacionadas ao pagamento são inseridas manualmente em um site de comércio eletrônico, em um fluxo do call center ou no terminal de PDV ou de pagamento. |
| O cartão está presente | Um termo que se refere a transações de pagamento em que um cartão físico é apresentado e usado em um terminal de pagamento conectado ao sistema de PDV do Microsoft Dynamics 365. |

## <a name="overview"></a>Visão Geral

Em geral, o termo *pagamentos de omni-channel* descreve a capacidade de criar uma ordem em um canal e atendê-la em outro canal. O segredo para o suporte a pagamento de omni-channel é preservar os detalhes de pagamento juntamente com os demais detalhes da ordem e, em seguida, usar esses detalhes de pagamento quando a ordem é recuperada ou processada em outro canal. Um exemplo clássico é o cenário "Comprar online, separar na loja". Nesse cenário, os detalhes de pagamento são adicionados quando a ordem é criada online. Eles são então cancelados no PDV para cobrar o cartão de pagamento do cliente no momento da retirada. 

Todos os cenários descritos neste tópico podem ser implementados usando o kit de desenvolvimento de software (SDK) de pagamentos padrão fornecido com o Commerce. O [Conector de Pagamento do Dynamics 365 para Adyen](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/adyen-connector?tabs=8-1-3) fornece uma implementação pronta para uso de todos os cenários descritos aqui. 

### <a name="prerequisites"></a>Pré-requisitos

Cada cenário descrito neste tópico requer um conector de pagamento que oferece suporte a pagamentos de omni-channel. O conector para Adyen pronto para uso também pode ser usado, pois oferece suporte aos cenários disponibilizados por meio do SDK de pagamentos. Para obter mais informações sobre como implementar conectores de pagamento e sobre o SDK de varejo em geral, visite a [Página inicial de varejo para profissionais e desenvolvedores de TI](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/dev-retail-home-page#payment-connectors).

#### <a name="supported-versions"></a>Versões com suporte

Os recursos de pagamento de omni-channel descritos neste tópico foram lançados como parte da versão 8.1.3 do Microsoft Dynamics 365 for Retail. 

#### <a name="card-present-and-card-not-present-connectors"></a>Conectores "cartão presente" e "cartão não presente"

O SDK de pagamentos depende de dois conjuntos de interfaces de programação de aplicativos (APIs) para pagamentos. O primeiro conjunto de APIs é denominado **iPaymentProcessor**. Ele é usado para implementar conectores de pagamento "cartão não presente" que podem ser usados em call centers e com a plataforma de comércio eletrônico do Microsoft Dynamics. Para obter informações sobre a interface **iPaymentProcessor**, consulte o white paper [Implementar um conector de pagamento e um dispositivo de pagamento](https://download.microsoft.com/download/e/2/7/e2735c65-1e66-4b8d-8a3c-e6ef3a319137/The%20Guide%20to%20Implementing%20Payment%20Connector%20and%20Payment%20Device_update.pdf), que abrande pagamentos. 

O segundo conjunto de APIs é denominado **iNamedRequestHandler**. Ele permite a implementação de integrações de pagamento "cartão presente" que usam um terminal de pagamento. Para obter mais informações sobre a interface **iNamedRequestHandler**, consulte [Criar uma integração de pagamento para um terminal de pagamento](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/end-to-end-payment-extension). 

### <a name="setup-and-configuration"></a>Instalação e configuração

Os seguintes componentes e etapas de configuração são necessários:

- **Integração de comércio eletrônico:** é necessária uma integração com o Commerce para dar suporte a cenários em que uma ordem se origina em uma vitrine online. Para obter mais informações sobre o SDK de comércio eletrônico do Retail, consulte [kit de desenvolvimento de software (SDK) da plataforma de comércio eletrônico](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/ecommerce-platform-sdk). Em um ambiente de demonstração, a vitrine de referência oferece suporte a cenários de pagamento de omni-channel. 
- **Configuração de pagamentos online:** a configuração do canal online deve incluir um conector de pagamento que foi atualizado para oferecer suporte a pagamentos de omni-channel. Como alternativa, o conector de pagamento pronto para uso pode ser usado. Para obter informações sobre como configurar o conector de pagamento de Adyen para lojas online, consulte [Conector de pagamento de Adyen](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/adyen-connector?tabs=8-1-3#e-commerce). Além das etapas de configuração do comércio eletrônico descritas neste tópico, o parâmetro **Permitir salvar informações de pagamento no comércio eletrônico** deve ser definido como **Verdadeiro** nas configurações do conector de Adyen. 
- **Configuração de pagamentos de omni-channel:** no back office, vá para **Retail e Commerce \> Configuração da sede \> Parâmetros \> Parâmetros compartilhados do Commerce**. Depois, na guia **Pagamentos de omni-channel**, define a opção **Usar pagamentos de omni-channel** como **Sim**. No Commerce versões 10.0.12 e posterior, essa configuração está no espaço de trabalho **Gerenciamento de Recursos**. Selecione o recurso **Pagamentos de omnicanal** e clique em **Habilitar agora**. 
- **Serviços de pagamento:** o call center usa o conector de pagamento padrão na página **Serviços de pagamento** para processar pagamentos. Para suportar cenários como "Comprar em uma call center, retirar na loja", esse conector de pagamento padrão deve ser o conector de pagamento de Adyen ou um conector de pagamento que atenda aos requisitos de implementação para pagamentos de omni-channel.
- **Serviço de TEF:** os pagamentos por meio de um terminal de pagamento devem ser configurados na Guia Rápida **Serviço de TEF** do perfil de hardware. O conector de Adyen oferece suporte a cenários de pagamentos de omni-channel prontos para uso. Outros conectores de pagamento que oferecem suporte à interface **iNamedRequestHandler** também podem ser usados se permitirem pagamentos de omni-channel.
- **Disponibilidade do conector de pagamento:** quando uma ordem é cancelada, as linhas de proposta de pagamento que são canceladas juntamente com a ordem incluem o nome do conector de pagamento que foi usado para criar as autorizações associadas a essa ordem. Quando a ordem é atendida, o SDK de pagamentos tenta usar o mesmo conector usado para criar a autorização original. Portanto, um conector de pagamento que tenha as mesmas propriedades do comerciante deve estar disponível para captura. 
- **Tipos de cartão:** para que os cenários de omni-channel funcionem corretamente, cada canal deve ter a mesma configuração para os tipos de proposta que podem ser usados para o omni-channel. Essa configuração inclui IDs de método de pagamento e IDs de tipo de cartão. Por exemplo, se o tipo de proposta **Cartões** tiver uma ID de **2** na configuração da loja online, ele deverá ter a mesma ID na configuração da loja de varejo. O mesmo requisito se aplica às IDs do tipo de cartão. Se o número do cartão **12** estiver definido como **VISA** na loja online, a mesma ID deverá ser configurada para a loja de varejo. 
- O Retail Modern POS para Windows ou Android com uma estação de hardware integrada — ou —
- Modern POS para iOS ou PDV em Nuvem com estação de hardware compartilhada conectada. 

### <a name="basic-principle-supporting-omni-channel-payments"></a>Princípio básico com suporte aos pagamentos de omni-channel

Os conectores de pagamento e os processadores de pagamento usam tokens ou referências para fazer referência a interações relacionadas a pagamentos com cartão. Por exemplo, quando uma autorização de pagamento é solicitada, uma referência a essa autorização é fornecida. Portanto, a autorização pode ser referenciada posteriormente, quando os fundos são capturados no momento do atendimento. Essa autorização é exclusiva do comerciante, do conector de pagamento e do processador. 

Se uma ordem criada online estiver sendo retirada na loja, os mesmos detalhes de pagamento dessa ordem deverão ser recuperados e usados. Quando os detalhes originais forem fornecidos como parte da solicitação para capturar um pagamento em relação à autorização original, o processador de pagamento poderá processar a solicitação e capturar o pagamento. 

Para referenciar corretamente o pedido online, um conector de pagamento "cartão não presente" que oferece ao mesmo processador também deve estar disponível. Dessa forma, o sistema de PDV pode ter um processador para pagamentos com "cartão presente", mas também pode ter acesso a outros conectores de pagamento para poder atender a ordens que são criadas em outros canais usando diferentes processadores de pagamento. 

## <a name="supported-scenarios"></a>Cenários com suporte

Os seguintes cenários de pagamento de omni-channel são compatíveis:

- Comprar online, retirar na loja
- Comprar em uma call center, retirar na loja
- Comprar na loja A, retirar na loja B
- Comprar na loja A, enviar ao cliente

    > [!NOTE]
    > Os pagamentos feitos no call center que mapeiam para a função de pagamento "Normal" devem ser marcados como **Pagamento antecipado** = **Sim** para ser refletido no valor devido ao recuperar a ordem no PDV. Pagamentos não antecipados do tipo "Normal" não são reconhecidos quando a ordem é recuperada no PDV. 

Variações desses cenários também são compatíveis. Por exemplo, uma ordem online pode incluir as duas linhas que serão enviadas ao cliente e as linhas que serão retiradas em uma loja. Todas as opções de atendimento de ordens são permitidas por meio de pagamentos de omni-channel. 

As seções a seguir descrevem as etapas para cada cenário e mostram como executar o cenário usando dados de demonstração. 

### <a name="buy-online-pick-up-in-store"></a>Comprar online, retirar na loja

Antes de começar, verifique se os seguintes pré-requisitos estão atendidos:

- Você tem uma loja de referência onde o conector de Adyen está configurado.
- A opção **Pagamentos de omni-channel** na página **Parâmetros compartilhados do Commerce** é definida como **Verdadeiro**. Em versões mais recentes, essa configuração foi movida para o espaço de trabalho **Gerenciamento de Recursos**, no qual você pode selecionar o recurso **Pagamentos de omnicanal** e clicar em **Habilitar agora**. 
- O conector de pagamento de Adyen é configurado para o registro de PDV de Houston.
- O Retail Modern POS para Windows ou Android com uma estação de hardware integrada — ou —
- Modern POS para iOS ou PDV em Nuvem com estação de hardware compartilhada conectada. 

Siga estas etapas para executar o cenário.

1. Na vitrine de referência, crie uma ordem para retirada na loja. Certifique-se de selecionar a loja de **Houston**. 
2. Siga as etapas de check-out e pague usando um número de cartão de crédito de teste. Você pode encontrar números de cartão de crédito de teste na [página de números de cartão de teste de Adyen](https://docs.adyen.com/development-resources/test-cards/test-card-numbers/#description).
3. No Commerce, use o trabalho em lotes **Sincronizar ordens** e a agenda de distribuição **P-001** para criar as ordens no back office.
4. No PDV, na página de boas-vindas, selecione a operação **Ordens para retirada** para ver as ordens de retirada na loja. 
5. Selecione uma ou mais linhas da ordem que foi criada na vitrine da referência e, em seguida, selecione **Retirar**.

    A ordem é recuperada do back office. 

6. Quando os detalhes da linha de ordem são recuperados do back office e um pagamento com cartão que pode ser usado para omni-channel é detectado, você é informado de que uma forma de pagamento está disponível.
7. Selecione **Usar a forma de pagamento disponível** para concluir a transação usando os detalhes do cartão que foram inseridos na vitrine de referência.

    As linhas da ordem são carregadas na página da transação e o saldo é 0 (zero). 

8. Selecione a guia **Pagamentos** para ver a linha de proposta retirada da ordem online. 
9. Selecione qualquer método de pagamento para concluir a transação. 

### <a name="buy-in-call-center-pick-up-in-store"></a>Comprar em uma call center, retirar na loja

1. No Commerce, na página **Serviço de atendimento ao consumidor**, insira **Karen Berg** na barra de pesquisa e depois selecione **Pesquisar**. 
3. Selecione **Karen Berg** nos resultados da pesquisa.
4. Depois que Karen for carregada na página **Serviço de atendimento ao consumidor**, selecione **Nova ordem de venda**.
5. Na página da nova ordem de venda, selecione **Cabeçalho** para exibir o cabeçalho da ordem. 
6. Na página **Cabeçalho da ordem**, define o site como **Central** e o depósito como **Houston**.
7. Na guia **Entregar**, defina o campo **Modo de entrega** como **60** para a retirada do cliente.
8. Selecione **Linhas** e depois adicione uma ou mais linhas à ordem. 
9. Selecione **Concluir** para inserir o fluxo de conclusão da ordem.
10. Role para baixo até a seção de pagamentos, selecione **Adicionar** e depois selecione uma linha na qual o tipo de método de pagamento está definido como **Cartões**. 
11. Selecione o sinal de adição (**+**) para adicionar um pagamento com cartão. 
12. Insira os detalhes de um número de cartão de crédito de teste encontrado na [página de números de cartão de teste de Adyen](https://docs.adyen.com/development-resources/test-cards/test-card-numbers/#description) e depois selecione **OK**.

    > [!NOTE]
    > Se a marca do cartão referente ao número do cartão que você digitou for diferente da marca selecionada quando o pagamento foi iniciado, o pagamento ainda será processado. Contudo, ele será postado nas contas mapeadas para a marca de cartão que você selecionou na etapa 10.

12. Selecione **OK** novamente para fechar a caixa de diálogo **Pagamentos de conclusão de ordem**.
13. Na página **Resumo da ordem de venda**, selecione **Enviar**.
14. No PDV, na página de boas-vindas, selecione a operação **Ordens para retirada** para ver as ordens de retirada na loja. 
15. Selecione uma ou mais linhas da ordem que foi criada na vitrine da referência e, em seguida, selecione **Retirar**.

    A ordem é recuperada do back office. 

16. Quando os detalhes da linha de ordem são recuperados do back office e um pagamento com cartão que pode ser usado para omni-channel é detectado, você é informado de que uma forma de pagamento está disponível.
17. Selecione **Usar a forma de pagamento disponível** para concluir a transação usando os detalhes do cartão que foram inseridos na vitrine de referência.

    As linhas da ordem são carregadas na página da transação e o saldo é 0 (zero).

18. Selecione a guia **Pagamentos** para ver a linha de proposta retirada da ordem online. 
19. Selecione qualquer método de pagamento para concluir a transação. 

### <a name="buy-in-store-a-pick-up-in-store-b"></a>Comprar na loja A, retirar na loja B

1. Inicie o PDV para a loja de Houston.
2. Na página **Transação**, adicione Karen Berg à transação usando o teclado numérico para inserir **2001**.
3. Adicione uma ou mais linhas à transação.
4. Selecione **Ordens** para ver as opções de ordem.
5. Selecione **Retirar tudo** e, depois, quando for solicitado, selecione **Ordem do cliente**.
6. Na barra de pesquisa, insira **Seattle** e depois selecione a loja de **Seattle** para retirada. 
7. Selecione **OK** para aceitar a data atual como a data de retirada.
9. Selecione **Pagar cartão** para iniciar o pagamento.
10. Conceda o pagamento com cartão para o valor que é devido para o depósito. 
11. Conclua o pagamento do depósito no terminal de pagamento. 
12. Após o depósito ser pago, selecione a opção de usar o mesmo cartão para preenchimento e aguarde a conclusão da ordem. 
13. Inicie o PDV para a loja de Seattle.
14. No PDV, na página de boas-vindas, selecione a operação **Ordens para retirada** para ver as ordens de retirada na loja. 
15. Selecione uma ou mais linhas da ordem que foi criada na vitrine da referência e, em seguida, selecione **Retirar**.

    A ordem é recuperada do back office. 

16. Quando os detalhes da linha de ordem são recuperados do back office e um pagamento com cartão que pode ser usado para omni-channel é detectado, você é informado de que uma forma de pagamento está disponível.
17. Selecione **Usar a forma de pagamento disponível** para concluir a transação usando os detalhes do cartão que foram inseridos na vitrine de referência.

    As linhas da ordem são carregadas na página da transação e o saldo é 0 (zero).

18. Selecione a guia **Pagamentos** para ver a linha de proposta retirada da ordem online. 
19. Selecione qualquer método de pagamento para concluir a transação. 

### <a name="buy-in-store-a-ship-to-customer"></a>Comprar na loja A, enviar ao cliente

1. Inicie o PDV para a loja de Houston.
2. Na página **Transação**, adicione Karen Berg à transação usando o teclado numérico para inserir **2001**.
3. Adicione uma ou mais linhas à transação.
4. Selecione **Ordens** para ver as opções de ordem.
5. Selecione **Remeter tudo** e, depois, quando for solicitado, selecione **Ordem do cliente**.
6. Na página do método de remessa, selecione **Padrão durante a noite** e, em seguida, selecione **OK** para aceitar a data de hoje como a data de envio. 
7. Selecione **OK** para aceitar a data atual como a data de retirada.
8. Selecione **Pagar cartão** para iniciar o pagamento.
9. Conceda o pagamento com cartão para o valor que é devido para o depósito. 
10. Conclua o pagamento do depósito no terminal de pagamento. 
11. Após o depósito ser pago, selecione a opção de usar o mesmo cartão para preenchimento e aguarde a conclusão da ordem.

Quando a ordem é retirada, embalada e faturada no back office, os detalhes de pagamento que são fornecidos no PDV serão usados para capturar os fundos para as mercadorias que estão sendo enviadas para o cliente. 

## <a name="scenario-details"></a>Detalhes do cenário

Além dos cenários básicos que acabamos de descrever, vários aprimoramentos foram feitos no SDK de pagamentos para oferecer suporte a pagamentos de omni-channel. 

### <a name="pos"></a>PDV

#### <a name="single-swipedip-for-customer-orders"></a>Passar/inserir apenas uma vez para ordens de cliente

Antes que o recurso de pagamentos de omni-channel fosse implementado, quando as ordens dos clientes que incluíam depósitos eram criadas no PDV, os clientes precisavam passar duas vezes o cartão: uma vez para pagar o depósito e uma vez para tokenizar o cartão para cumprimento subsequente da ordem. Quando o recurso de tokenização de omni-channel está ativado, os clientes devem passar o cartão apenas uma vez para pagar o depósito e autorizar o valor devido para as mercadorias que serão atendidas posteriormente. No momento do cumprimento, os fundos autorizados são capturados. Antes de o recurso de tokenização de omni-channel ser implementado, apenas um token de cartão recorrente era criado para o cumprimento subsequente da ordem. Portanto, os fundos para o cumprimento pendente não foram autorizados e, como esses fundos não estavam sendo mantidos para essa compra específica, era menos provável que eles pudessem ser capturados posteriormente.

> [!NOTE]
> Não é possível passar apenas uma vez na versão 8.1.3 do Retail. Ordens de clientes na versão 8.1.3 usam o mesmo fluxo que foi usado antes que o recurso de tokenização de omni-channel fosse implementado. 

### <a name="cards-that-cant-issue-recurring-card-tokens"></a>Cartões que não podem emitir tokens de cartão recorrentes

Alguns cartões não podem ser usados para pagamentos de omni-channel, porque eles não permitem a emissão de tokens de cartão recorrentes. Quando uma ordem é criada no PDV, se o depósito é pago usando um cartão que não é compatível com tokens de cartão recorrentes, o fluxo de tokenização de cartão anterior é usado. Portanto, um cliente que deseja fornecer um pagamento que será usado para o cumprimento subsequente da ordem deve apresentar um segundo cartão. Se o segundo cartão não permitir tokens de cartão recorrentes, a ação de tokenização será recusada e o caixa será solicitado a pedir ao cliente que forneça um cartão diferente. 

### <a name="using-a-different-card"></a>Usando um cartão diferente

Um cliente que chega à loja para retirada de ordem tem a opção de usar um cartão diferente. Quando o caixa recebe o prompt **Usar a forma de pagamento disponível** no momento da retirada da ordem, ele pode perguntar se o cliente quer usar o mesmo cartão. Se o cliente tiver perdido o cartão usado para criar a ordem e quiser pagar pela ordem usando um cartão diferente, o caixa poderá selecionar **Usar uma forma de pagamento diferente**. Se o cliente voltar mais tarde para buscar mais itens da mesma ordem, se a autorização original do cartão ainda for válida, o caixa poderá perguntar novamente se o cliente deseja usar esse cartão.

### <a name="invalid-authorizations"></a>Autorizações inválidas

Se o cartão usado para criar uma ordem não for mais válido, quando os produtos forem selecionados para retirada, a solicitação de captura de pagamento falhará. O conector de pagamento de PDV tentará criar uma autorização e capturar usando os mesmos detalhes do cartão. Se a nova autorização ou captura falhar, o caixa será informado de que o pagamento não pôde ser processado. O caixa deve então receber um novo pagamento do cliente. 

### <a name="multiple-available-payments"></a>Vários pagamentos disponíveis

Quando uma ordem que tem várias propostas e várias linhas é selecionado, o caixa primeiro recebe o prompt **Usar a forma de pagamento disponível**. Se houver vários cartões, quando o caixa selecionar **Usar a forma de pagamento disponível**, as linhas de cartão existentes serão capturadas até que o saldo seja atendido para as mercadorias que estão sendo retiradas atualmente. O caixa não terá a opção de selecionar o cartão que deve ser usado para as mercadorias que estão sendo retiradas. 

## <a name="related-topics"></a>Tópicos relacionados

- [Perguntas frequentes sobre pagamentos](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/payments-retail)
- [Conector de Pagamento do Dynamics 365 para Adyen](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/adyen-connector?tabs=8-1-3)
- [Configurar BOPIS em um ambiente de avaliação do Dynamics 365 Commerce](https://docs.microsoft.com/dynamics365/commerce/cpe-bopis)

