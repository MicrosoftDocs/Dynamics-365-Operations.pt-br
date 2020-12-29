---
title: Encargos automáticos avançados de omni-channel
description: Este tópico descreve recursos para gerenciar encargos adicionais da ordem para ordens do canal do Commerce usando recursos avançados de encargos automáticos.
author: hhaines
manager: annbe
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10
ms.openlocfilehash: 2d463bf01659aeb6599023ce46da0c604f8eeff0
ms.sourcegitcommit: 4c6d31f3ebd88212d3d1497a4bba9c64c5300444
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "4410339"
---
# <a name="omni-channel-advanced-auto-charges"></a>Encargos automáticos avançados de omnicanal

[!include [banner](includes/banner.md)]

Este tópico fornece informações sobre a configuração e a implementação de recursos avançados da encargos disponíveis na versão 10.0 do Dynamics 365 for Retail.

Quando os recursos avançados de encargos diversos forem habilitados, as ordens criadas em qualquer canal do Commerce suportado (ponto de venda, (PDV) call center e online) podem ter a vantagem das configurações de [encargos automáticos](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services) definidas no aplicativo ERP para o cabeçalho e encargos relacionados a linha-nível.

Em versões anteriores à versão 10.0 do Retail, as configurações de [encargo automático](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services) estão acessíveis somente pelas ordens criadas nos canais de call center e de comércio eletrônico. Em versões 10.0 e posteriores várias ordens criadas de PDV podem aproveitar as configurações de encargos automáticos. Dessa forma, diversos encargos adicionais podem ser adicionados sistematicamente às transações de vendas.

Ao usar versões anteriores à versão 10.0, um usuário do PDV deverá inserir manualmente qualquer taxa de remessa durante a criação de uma transação PDV "remeter tudo" ou "remeter selecionado". Quando os recursos de encargos diversos do aplicativo forem utilizados considerando como os encargos são gravados na ordem, um cálculo sistemático é fornecido – o cálculo considera a entrada de usuário para determinar o valor de encargos. Os encargos só podem ser adicionados como encargos únicos relacionados à "remessa" e não podem ser editados ou alterados facilmente no PDV, após serem criados.

O uso de solicitações manuais para adicionar encargos de remessa ainda está disponível nas versões 10.0 e posterior. Se uma organização não habilitar o parâmetro **Encargos Automáticos Avançados**, o PDV solicita que a entrada manual de encargos permaneça igual.

Com o recurso avançado de encargos automáticos, os usuários do PDV podem ter cálculos sistemáticos para quaisquer encargos diversos definidos com base nas tabelas de configuração de encargos automáticos. Além disso, os usuários terão a capacidade de adicionar ou editar um número ilimitado de encargos e taxas para qualquer transação de vendas de PDV em nível de cabeçalho ou linha (para cash and carry ou ordem do cliente).

## <a name="enabling-advanced-auto-charges"></a>Como habilitar encargos automáticos avançados

Na página **Retail e Commerce \> Configuração da sede \> Parâmetros \> Parâmetros do Commerce**, vá para a guia **Ordens do cliente**. Na guia rápida **Encargos**, defina **Usar Encargos Automáticos Avançados** como **Sim**.

![Parâmetro de Encargos automáticos avançados](media/advancedchargesparameter.png)

Quando os encargos automáticos avançados forem habilitados, não será mais solicitado para os usuários inserirem manualmente um encargo de remessa no terminal de PDV, ao criar uma ordem do cliente remeter tudo ou remeter selecionado. Os encargos de ordem PDV são calculados sistematicamente e adicionados à transação de PDV (se for encontrada uma tabela de encargos automáticos correspondente que atenda aos critérios da ordem que está sendo criada). Os usuários também podem adicionar ou manter os encargos em nível de linha ou cabeçalho através de operações de PDV recém-adicionadas que podem ser adicionadas aos layouts de tela de PDV.

Quando os encargos automáticos avançados são ativados, os **Parâmetros do Commerce** do **Código de encargos de remessa** e **Encargos de remessa de reembolso** não são mais utilizados. Esses parâmetros só serão aplicáveis se o parâmetro **Usar encargos automáticos avançados** for definido como **Não**.

Antes de habilitar este recurso, teste e treine seus funcionários, pois o recurso habilitado alterará o fluxo de processo empresarial de como os encargos de remessa e outros encargos são calculados e adicionados às ordens de venda de PDV. Certifique-se de que você entende o impacto do fluxo do processo para criação de transações de PDV. Para ordens de call center e de comércio eletrônico, o impacto ao habilitar os encargos automáticos avançados é mínimo. Os aplicativos de call center e de comércio eletrônico continuarão tendo o mesmo comportamento que tiveram relacionado historicamente às tabelas de encargos automáticos ao calcular taxas de ordem adicionais. Os usuários do canal do call center continuarão tendo a capacidade de editar manualmente quaisquer encargos automáticos calculados pelo sistema em nível de cabeçalho ou linha, ou adicionar diversos encargos adicionais em nível de cabeçalho ou linha.

## <a name="additional-pos-operations"></a>Operações adicionais de PDV

Para que os encargos automáticos avançados trabalhem adequadamente no ambiente do aplicativo de PDV, novas operações de PDV foram adicionadas. Essas operações devem ser adicionadas aos seus [layouts de tela de PDV](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts) e implantadas nos dispositivos de PDV, conforme você implanta os encargos automáticos avançados. Se essas operações não forem adicionadas, os usuários não poderão manter ou gerenciar encargos diversos em transações de PDV e não terá nenhuma maneira de ajustar ou de alterar os valores de encargos diversos calculados sistematicamente com base nas configurações de encargos automáticos. No mínimo, sugerimos que você implante a operação **Gerenciar encargos** em seu layout de PDV.

As novas operações são as seguintes.

- **142 - Gerenciar encargos** – use essa operação para permitir que os usuários de PDV exibam e editem encargos diversos para a transação de PDV que foram adicionados manualmente ou sistematicamente por meio de cálculos de encargos automáticos.
- **141 - Adicionar encargos de cabeçalho** – Use esta operação para fornecer ao usuário a capacidade de adicionar manualmente um encargo diverso em nível de cabeçalho para qualquer transação de venda de PDV (e selecione o código de encargos a ser usado).
- **140 - Adicionar encargos de linha** – Use esta operação para fornecer ao usuário a capacidade de adicionar manualmente um encargo diverso em nível de linha para qualquer transação de venda de PDV (e selecione o código de encargos a ser usado).
- **143 - Calcular encargos** – Use esta operação para executar o recálculo completo de encargos para a transação de vendas. Todos os encargos automáticos substituídos pelo usuário serão recalculados com base na configuração atual do carrinho.

Como todas as operações com PDV, as configurações de segurança podem ser feitas para exigir aprovação do gerente para executar a operação.

É importante observar que as operações de PDV listadas acima também podem ser adicionadas ao layout do PDV, mesmo se o parâmetro **Usar encargos automáticos avançados** estiver desabilitado. Nesse cenário, as organizações ainda terão benefícios adicionais de poder visualizar as cobranças adicionadas manualmente e editá-las usando a operação **Gerenciar encargos**. Os usuários também podem usar as operações **Adicionar encargos de cabeçalho** e **Adicionar encargos de linha** para transações de PDV mesmo quando o parâmetro **Usar encargos automáticos avançados** está desabilitado. A operação **Calcular encargos** tem menos funcionalidade se usada quando **Usar encargos automáticos avançados** está desabilitado. Nesse cenário, nada seria recalculado e todos os encargos adicionados manualmente à transação seriam redefinidos para US $ 0,00.

## <a name="use-case-examples"></a>Exemplos de caso de uso

Nesta seção, exemplos de casos de uso são apresentados para ajudar a entender a configuração e o uso de encargos automáticos e encargos diversos dentro do contexto de ordens do canal. Estes exemplos mostram o comportamento de aplicativo quando o parâmetro **Usar Encargos Automáticos Avançados** for habilitado.

### <a name="auto-charges-header-charges-example"></a>Exemplo de encargos do cabeçalho de encargos automáticos

#### <a name="use-case-scenario"></a>Cenário de caso de uso

Um varejista deseja adicionar encargos de frete automaticamente quando as transações forem criadas em qualquer canal do Commerce que exija a remessa de produtos ao cliente. O varejista oferece dois métodos de entrega: Terrestre e aéreo. Se um cliente escolher a entrega aérea e o valor da ordem for menor que US$ 100, o varejista quer cobrar um frete de US$ 10,00 do cliente. Se a ordem for maior que US$ 100 e o cliente escolher a entrega terrestre, o cliente não cobrará taxas de frete adicional. Se o cliente optar pelo método de entrega aéreo de todas as ordens, independentemente do valor total, será cobrado uma taxa de frete de US$ 20,00.

#### <a name="setup-and-configuration"></a>Instalação e configuração

Esse cenário requer a configuração de duas tabelas de encargos automáticos.

Vá para **Contas a receber \> Configuração de encargos \> Encargos automáticos**.

Configurar dois encargos automáticos em nível de cabeçalho diferentes. Configure um para "Modo terrestre" e outro para "Modo aéreo" de entrega. Para este cenário, configure-s para serem usados para "Todos os clientes".

Para os encargos de entrega terrestre, na seção de linhas da página **Encargos automáticos**, defina um encargo que será aplicado para ordens entre US$ 0,01 e US$ 100 como US$ 10,00. Crie outra linha de encargos para indicar que ordens acima de US$ 100,01 não terão encargos.

![Exemplo de duas tabelas de encargos automáticos](media/headerchargesexample.png)

Para os encargos de entrega aérea, na seção de linhas do formulário de encargos automáticos, defina um encargo de US$ 20,00 que será aplicado a todas as ordens (entre um valor de US$ 0,01 a US$ 9.999.999).

Envie as alterações para o Commerce Scale Unit/BD de Canal, de forma que o PDV possa utilizá-las ao executar o trabalho **agenda de distribuição 1040**.

#### <a name="sales-processing-for-this-scenario"></a>Processamento de vendas deste cenário

Depois que as etapas de configuração acima forem concluídas e as alterações forem aplicadas ao banco de dados do canal, qualquer ordem de cliente ou transação de venda criada no PDV, call center ou nos canais de comércio eletrônico com métodos de entrega terrestre ou aéreo definidos em nível de cabeçalho utilizará esses encargos e os aplicará automaticamente à venda.

Neste momento, os encargos serão aplicados a todas as transações de vendas criadas dentro da entidade legal que utiliza esses modos de entrega, pois não há funcionalidade para designar que uma configuração de encargo automático somente será aplicada a um canal de vendas específico.

Para cenários de PDV e comércio eletrônico, como não há "cabeçalho" definido claramente nessas ordens, os encargos em nível de cabeçalho somente serão aplicados se todas as linhas de vendas na transação forem definidos para remessa com o mesmo modo de entrega. Se houver “modos mistos” de atendimento em transações criadas por PDV ou comércio eletrônico, somente encargos automáticos em nível de linha serão considerados e aplicados.

Nos cenários de call center, o usuário tem controle sobre a definição do modo de entrega no cabeçalho da ordem, portanto os encargos em nível de cabeçalho se aplicarão para essas ordens, mesmo se algumas linhas de venda forem configuradas para usar um modo de entrega diferente. Os encargos em nível de cabeçalho para ordens do call center sempre serão baseados no modo de entrega definido em nível de cabeçalho da ordem da ordem de venda.

### <a name="auto-charges-line-charges-example"></a>Exemplo de encargos de linha de encargos automáticos

#### <a name="use-case-scenario"></a>Cenário de caso de uso 

Um varejista deseja adicionar um encargo adicional a um cliente para taxas de instalação quando o cliente comprar um modelo de computador específico. Este computador requer ações de configuração adicional, não opcional que o varejista executará para o cliente. O varejista informou aos clientes que haverá uma taxa adicional para esta instalação. O varejista prefere gerenciar os encargos relacionados a esta taxa separadamente do preço de venda do produto para fins de relatório financeiro. Uma taxa de instalação de US$ 19,99 será cobrada do cliente quando este computador específico for comprado em qualquer canal.

#### <a name="setup-and-configuration"></a>Instalação e configuração

Esse cenário requer a configuração de uma tabela de encargos automáticos em nível de linha.

Vá para **Contas a Receber \> Configuração de encargos \> Encargos automáticos**.

Defina o menu suspenso **Nível** como **Linha** e crie um novo registro de encargos automáticos para todos os clientes e para o produto específico ou grupo de produtos onde as taxas de instalação serão cobradas.

![Exemplo de uma tabela de encargos automáticos em nível de linha](media/linechargesexample.png)

Envie as cobranças para o Commerce Scale Unit/BD de Canal, de forma que o PDV possa utilizá-las ao executar o trabalho **agenda de distribuição 1040**.

#### <a name="sales-processing-for-this-scenario"></a>Processamento de vendas deste cenário

Depois que as etapas de configuração acima forem concluídas e as alterações forem aplicadas ao banco de dados do canal, qualquer ordem de cliente ou transação de venda criada no PDV, call center ou nos canais de comércio eletrônico que têm este item na ordem dispararão um encargo em nível de linha para ser adicionado sistematicamente à ordem total.

Neste momento, os encargos serão aplicados a toda linha de vendas que corresponder à configuração de encargos automáticos em nível de linha dentro da entidade legal, pois não há funcionalidade para configurar um encargo automático em nível de linha para ser aplicada somente a um canal de vendas específico.

### <a name="manual-header-charges-example"></a>Exemplo de encargos de cabeçalho manual

#### <a name="use-case-scenario-description"></a>Descrição do cenário de caso de uso

Um varejista estiver fazendo uma exceção a processos comuns, oferecendo uma entrega em domicílio especial de produtos para um cliente que solicitar os produtos na loja. O fornecedor e o cliente que concordaram o cliente pagará uma taxa de entrega adicional de US$ 25 por este serviço. O tomador da ordem precisa adicionar esta taxa adicional à transação. Como a taxa é uma taxa ampla e não está relacionada a nenhum produto único da ordem, será utilizado o encargo do cabeçalho.

#### <a name="setup-and-configuration"></a>Instalação e configuração

Certifique-se de que o código de encargo que será usado neste cenário foi configurado adequadamente, indo para **Contas a Receber \> Configuração de Encargos \> Encargos** para definir um código de encargos apropriado para o cenário.

![Exemplo de encargos](media/chargesexample.png)

Se o encargo é considerado um encargo relacionado a “remessa” com a finalidade de descontos ou promoções relacionadas a remessa, defina **Encargo de remessa** no código de encargos como **Sim**. Se este encargo também puder ser reembolsado durante o processamento de uma transação de devolução no aplicativo PDV, defina **Reembolsável** como **Sim**. O sinalizador **Reembolsável** somente é aplicável quando o parâmetro **Usar encargos automáticos avançados** for definido como **Sim**.

Envie as cobranças para o Commerce Scale Unit/BD de Canal, de forma que o PDV possa utilizá-las ao executar o trabalho **agenda de distribuição 1040**.

A operação **Adicionar encargos de cabeçalho** deve ser definida no [Layout da tela de PDV](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts) de modo que um botão fique acessível ao usuário do PDV possa chamar esta operação (operação) 141. As alterações do layout da tela devem ser distribuídas para canal e também através da função de agenda de distribuição.

#### <a name="sales-processing-of-manual-header-charges"></a>Processamento de vendas de encargos de cabeçalho manual

Para executar o cenário no aplicativo do PDV, o usuário do PDV criará a transação de venda como de costume, adicionando os produto e as outras configurações à venda. Antes de coletar o pagamento, o usuário deve executar a operação **Adicionar encargos de cabeçalho**, que solicitará que o usuário selecione um código de encargos e informe o valor dos encargos. Depois que o usuário concluir o processo, o encargo será adicionado à ordem de venda como um encargo em nível de cabeçalho.

Esse processo pode ser aplicado no call center usando o recurso existente **Encargos** localizado na guia **Venda** na barra de ferramentas. Na página **Manter encargos**, o usuário pode adicionar uma nova linha de encargos ao cabeçalho da ordem.

### <a name="manual-line-charges-example"></a>Exemplo de encargos de linha manual

#### <a name="use-case-scenario"></a>Cenário de caso de uso

Um cliente solicitou que dois de cinco itens da mesma ordem de venda sejam embrulhados para presente. O varejista oferece este serviço opcional com uma taxa de US$ 2,00 por item. O tomador da ordem precisa adicionar essas taxas aos itens específicos que precisam ser embrulhados para presente.

#### <a name="setup-and-configuration"></a>Instalação e configuração

Certifique-se de que o código de encargo que será usado neste cenário foi configurado adequadamente, indo para **Contas a Receber \> Configuração de Encargos \> Encargos** para definir um código de encargos apropriado para o cenário.

Se o encargo tiver que ser considerado um encargo relacionado à “remessa” com a finalidade de descontos ou promoções relacionados à remessa, defina **Encargo de remessa** no código de encargos como **Sim**. Se o encargo também puder ser reembolsado durante o processamento de uma transação de devolução no aplicativo PDV, defina **Reembolsável** como **Sim**. O sinalizador **Reembolsável** somente é aplicável quando o parâmetro **Usar encargos automáticos avançados** for definido como **Sim**.

Envie as cobranças para o Commerce Scale Unit/BD de Canal, de forma que o PDV possa utilizá-las ao executar o trabalho **agenda de distribuição 1040**.

A operação **Adicionar encargos de linha** deve ser configurado no [Layout da tela de PDV](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts) de modo que um botão fique acessível ao usuário do PDV possa chamar esta operação (operação) 140. As alterações do layout da tela devem ser distribuídas para canal e também através da função de agenda de distribuição.

#### <a name="sales-processing-of-the-manual-line-charge"></a>Processamento de vendas de encargo de linha manual

Para executar o cenário no aplicativo do PDV, o usuário do PDV criará a transação de venda como de costume, adicionando os produto e as outras configurações à venda. Antes de coletar o pagamento, o usuário deve selecionar a linha específica onde o encargo será aplicado da exibição da lista de itens de PDV e executar a operação **Adicionar encargo de linha**. Será solicitado que o usuário selecione um código de encargos e insira o valor de encargos. Depois que o usuário concluir o processo, o encargo será vinculado à linha e adicionado à ordem total como um encargo em nível de linha. O usuário pode repetir o processo para adicionar encargos de linha adicionais para outras linhas de itens na transação, se necessário.

O mesmo processo poderá ser aplicado no call center usando o recurso “manter encargos” localizado no menu suspenso **Finanças** na seção **Linhas de ordem de venda** na página **Ordem de venda**. A seleção dessa opção abrirá a página **Manter encargos** onde o usuário pode adicionar um novo encargo específico de linha à transação.

## <a name="additional-features"></a>Recursos adicionais

### <a name="editing-charges-on-a-pos-sales-transaction"></a>Editando encargos em uma transação de vendas de PDV

A operação **Gerenciar encargos** (142) deve ser adicionada ao [Layout da tela do PDV](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts) de forma que um usuário possa exibir e editar ou substituir todos os encargos diversos calculados pelo sistema ou criados manualmente em nível de cabeçalho ou de linha. Se a operação não for adicionada, os usuários não poderão ajustar o valor de encargos na transação PDV, não poderão exibir os detalhes dos encargos, como o tipo de código de encargos vinculado ao encargo.

Na página **Gerenciar encargos** no PDV, o usuário pode exibir os detalhes dos encargos em nível de linha e de cabeçalho. O usuário pode usar a função **Editar** disponível nesta página para fazer alterações no valor cobrado para uma linha de encargos específica. Depois que uma linha de encargos for substituída manualmente, ela não será recalculada sistematicamente a menos que o usuário inicie a operação **Recalcular encargos**

Se o **Código de motivo de substituição do encargo** for definido na página de configuração **Parâmetros do Commerce** , será solicitado que o usuário forneça um código de motivo quando os encargos forem modificados no aplicativo PDV.

Se os códigos do motivo forem capturados para encargos substituídos, um novo relatório também ficará disponível para revisar e auditar essas substituições. O relatório pode ser localizado em **Retail e Commerce \> Consultas e relatórios \> Histórico de substituições de encargos**.

### <a name="refunding-charges-on-a-pos-return-transaction"></a>Reembolso de encargos em uma transação de devolução de PDV

Se o parâmetro **Usar encargos automáticos avançados** estiver definido como **Sim**, o parâmetro do Commerce existente **Reembolsar encargos de remessa** não será mais aplicável. Para indicar que os encargos devem ser sistematicamente reembolsados a um cliente ao usar os encargos avançados, certifique-se de que o código de encargos diversos foi configurado como **Reembolsável** na página de configuração **Código de encargos** . Verifique se as configurações foram sincronizadas nos bancos de dados do canal do Commerce através do processamento da agenda de distribuição.

### <a name="refunding-charges-on-a-return-order-transaction"></a>Reembolso de encargos em uma transação de ordem de devolução

Os encargos não são reembolsados sistematicamente para as **Ordens de devolução** criadas no Commerce. Os usuários precisam selecionar a opção **Copiar encargos** ao criar a **Ordem de devolução**. Se a opção **Copiar encargos** não for selecionada, os encargos da transação de venda original não serão reembolsados automaticamente. Se **Copiar encargos** for selecionada, todos os encargos serão copiados para a ordem de devolução e o usuário poderá editar ou remover os encargos que ele não quer reeembolsar. O processo da ordem de devolução do call center atualmente não reconhece o sinalizador **Reembolsável** na configuração **Código de encargos** .

### <a name="configuring-pos-receipts-to-show-charges"></a>Configurando recibos do PDV para mostrar encargos

Os seguintes elementos de recebimento foram adicionados à linha e ao rodapé do recibo para oferecer suporte à funcionalidade avançada de encargos automáticos.

- **Encargos da Remessa da Linha** – Este elemento em nível de linha pode ser usado para recapitular os códigos de encargos específicos que foram aplicados à linha de venda. Somente códigos de encargos que foram marcados como encargos de **Remessa** na página **Código de encargos** serão exibidos aqui.
- **Outros Encargos da Linha** – Este elemento em nível de linha pode ser usado para recapitular os códigos de encargos específicos que não são de remessa que foram aplicados à linha de venda. São códigos de encargos em que o sinalizador **Remessa** na página **Código de encargos** não foi ativado.
- **Detalhes dos Encargos de Remessa de Ordem** – Este elemento em nível de rodapé exibe as descrições dos códigos de encargo aplicados à ordem que foram marcados como encargos de **Remessa** na página de configuração **Código de encargos**.
- **Encargos de Remessa de Ordem** – Este elemento em nível de cabeçalho mostra o valor monetário dos encargos relacionados à remessa.
- **Detalhes dos Outros Encargos da Ordem** – Este elemento em nível de rodapé exibe a descrição dos códigos de encargos aplicada à ordem que não foram marcados como encargos relacionados à remessa.
- **Outros Encargos da Ordem** – Este elemento em nível de cabeçalho exibe o valor monetário de outros encargos não relacionados à remessa.

Recomendamos que a organização também adicione campos de texto livre no rodapé do recibo para definir as áreas nas quais os encargos serão recapitulados.

### <a name="preventing-charges-from-being-calculated-until-the-pos-order-is-completed"></a>Impedindo que os encargos sejam calculados até que a ordem de PDV seja concluída

Algumas organizações pode preferir aguardar até que o usuário conclua a adição de todas as linhas de venda na transação de PDV antes de calcular os encargos. Para evitar o cálculo de encargos, conforme os itens são adicionadas à transação PDV, ative o parâmetro **Cálculo de encargo manual** no parâmetro **Perfil de funcionalidade** usado pela loja. Habilitar esse parâmetro exigirá que o usuário do PDV use a operação **Calcular totais** quando terminarem de adicionar os produtos à transação de PDV. A operação **Calcular totais** disparará o cálculo de encargos automáticos para o cabeçalho ou linha da ordem, conforme aplicável.

### <a name="charges-override-reports"></a>Relatórios de substituições de encargos

Se os usuários substituírem manualmente os encargos calculados ou adicionarem um encargo manual à transação, esses dados estarão disponíveis para auditoria no relatório **Histórico de substituições de encargos**. vO relatório pode ser acessado de **Retail e Commerce \> Consultas e relatórios \> Histórico de substituições de encargos**. É importante observar que os dados necessários para esse relatório são importados do banco de dados do canal para a matriz por meio dos trabalhos de agendamento da distribuição "P". Portanto, as informações sobre substituições executadas apenas no PDV podem não estar imediatamente disponíveis nesse relatório até que esse trabalho tenha carregado os dados da transação da loja na matriz.

## <a name="additional-resources"></a>Recursos adicionais

[Habilitar e configurar encargos automáticos por canal](auto-charges-by-channel.md)

[Ratear encargos do cabeçalho para as linhas de vendas correspondentes](pro-rate-charges-matching-lines.md)

