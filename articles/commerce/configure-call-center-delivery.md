---
title: Configurar modos de entrega e encargos do call center
description: Este tópico descreve como configurar modos de entrega e encargos para uma ordem do call center no Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 04/26/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 9919e76b5e3eb1a43c5a0ecd5dda1462bedad4f2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410094"
---
# <a name="configure-call-center-delivery-modes-and-charges"></a>Configurar modos de entrega e encargos do call center

[!INCLUDE [banner](includes/banner.md)]

Quando uma ordem de venda é feita no Dynamics 365 Commerce, se a pessoa que inseriu a ordem de venda está vinculada a um canal do call center, a lógica e as regras são usadas para validar o modo de entrega e calcular os encargos da ordem.

Quando você cria uma ordem de venda, é possível selecionar um modo de entrega no cabeçalho de ordem de venda e nas linhas de ordem de venda. Por padrão, o modo de entrega selecionado no cabeçalho é usado para todas as linhas de ordem de venda. Entretanto, você pode substituir o modo padrão de entrega nas linhas individuais de venda, como necessário. Você também pode definir um modo de entrega de um registro de cliente. Então, quando as ordens são criadas para o cliente, esse modo de entrega é usado por padrão no cabeçalho da ordem de venda.

O Commerce tem recursos que permitem aos usuários limitar os modos de entrega que podem ser usados por um canal, os que podem ser usados para um produto e os que são válidos para destinos de envio específicos. Os encargos também podem ser definidos para que taxas adicionais sejam adicionadas à ordem de um cliente, com base nos modos de entrega selecionados para a ordem de venda e no valor total da ordem.

## <a name="define-delivery-modes"></a>Definir modos de entrega

Antes de especificar quais modos de entrega podem ser usados para as ordens do call center e definir as regras e encargos associados, você deve definir os modos de entrega. Vá para **Vendas e marketing \> Configuração \> Distribuição \> Modos de entrega**. Selecione **Novo** para criar um novo modo de entrega. Como alternativa, selecione um modo de entrega existente na lista e, em seguida, selecione **Editar** para fazer alterações.

No campo **Modo de entrega**, você pode inserir qualquer combinação de caracteres alfanuméricos, com base nos seus requisitos de negócios. Em seguida, você usar o campo **Descrição** para fornecer contexto adicional. Os campos **Grupo de encargos** e **Expedir** são opcionais e serão explicados em mais detalhes posteriormente neste tópico.

Na FastTab **Canais de comércio** adicione qualquer canal que deve ter permissão para usar o modo de entrega quando transações de vendas forem criadas nesse canal.

Na guia rápida **Produtos** você pode especificar quais produtos e/ou categorias de produto o modo de entrega pode e não pode ser usado. Por exemplo, se um produto não puder ser enviado por via aérea devido a restrições de material perigoso (hazmat), certifique-se de que o produto ou a categoria de produto esteja excluído de todos os modos de entrega que envolvam o transporte aéreo.

Na guia rápida **Endereços**, você pode especificar em quais países ou regiões, ou estados, o modo de entrega pode e não pode ser usado. Por exemplo, ordens que são enviados ao Havaí ou ao Alasca não estão qualificadas para entrega em terra. Portanto, esses estados devem ser excluídos de qualquer modo de entrega associado a um serviço de entrega em terra, mas incluídos em qualquer modo de entrega associado a um serviço de entrega aérea.

## <a name="validate-delivery-modes-for-a-call-center-order"></a>Valide modos de entrega para uma ordem de call center

Após os modos de entrega serem definidos, você deve executar o lote de processo **Processar modos de entrega**. Esse trabalho disponibiliza os modos de entrega para que possam ser usados em processos de ordem de venda para canais. Para executar o trabalho **Processar modos de entrega**, vá para **Varejo e Comércio \> TI de Varejo e Comércio \> Processar modos de entrega**. Esse trabalho deve ser executado sempre que novos modos de entrega forem adicionados a um canal ou forem feitas alterações nos relacionamentos de modo/canal de entrega existentes.

Depois de executar o trabalho em lotes **Processar modos de entrega**, você pode ir para **Varejo e Comércio \> Canais \> Call centers \> Todos os call centers**. Na página **Todos os call centers**, na Página Ação, na guia **Configurar**, selecione **Modos de entrega**. A página **Modos de entrega** lista todos os modos de entrega válidos para o canal de call center selecionado. Para editar os modos de entrega existentes ou adicionar novos modos de entrega, selecione **Gerenciar modos de entrega**. Observe que o trabalho **Processar modos de entrega** deve ser executado sempre que forem feitas alterações.

## <a name="define-charges-for-delivery-services"></a>Defina encargos para serviços de entrega

Quando as ordens de venda são criadas para clientes, uma empresa pode querer adicionar cobranças que são calculadas automaticamente com base nos modos de entrega selecionados para a ordem. Esses encargos podem ser configurados para que sejam iguais para todos os clientes e modos de entrega. Como alternativa, encargos podem variar, dependendo do cliente e/ou os modos de entrega selecionados para a ordem de venda.

Para definir os encargos, vá para **Varejo e Comércio \> Configuração de canal \> Encargos \> Encargos automáticos**. Selecione **Novo** para adicionar novos encargos. Como alternativa, selecione uma entrada existente, e selecione **Editar**.

Os encargos podem ser definidos de modo que sejam calculados no nível do cabeçalho da ordem ou das linhas da ordem. Use o campo **Nível** para selecionar o nível desejado.

Os encargos podem ser definidos para um cliente específico, um grupo de clientes ou todos os clientes. No campo **Código da conta** , selecione **Tabela** para definir encargos aplicados apenas a um cliente específico. Selecione **Grupo** para definir encargos a um grupo específico de clientes. Selecione **Tudo** para aplicar os encargos a cada cliente que fizer uma ordem de venda que usa o modo de entrega relacionado. Se você selecionou **Tabela** ou **Grupo** no campo **Código de conta**, selecione o cliente ou grupo de cliente no campo **Relação de conta**.

Os encargos poderão ser configurados de forma que sejam aplicados para modo de entrega específico, grupo do modo de entrega ou todos os modos de entrega. Se você selecionar **Tabela** no campo **Código do modo de entrega** , selecione um modo de entrega específico no campo **Relação de modo de entrega** . Se você selecionar **Grupo**, selecione um grupo do modo de entrega no campo **Relação de modo de entrega** . Os grupos de modo de entrega são definidos em **Varejo e Comércio \> Configuração de canal \> Encargos \> Grupo de encargos de entrega**. Eles podem ser vinculados a um ou mais modos de entrega na página **Modos de entrega** . Se você selecionar um grupo ao definir encargos, qualquer modo de entrega vinculado ao grupo de entrega selecionado usará esses encargos. Por fim, se você selecionar **Tudo** no campo **Código do modo de entrega**, todos os modos de entrega usam os encargos. Portanto, não selecione um valor no campo **Relação de modo de entrega** .

Na seção **Linhas** , você pode definir uma ou mais cobranças por moeda, conforme necessário. Os encargos devem ser vinculados a um código de encargos diversos que defina regras financeiras de lançamento do encargo. O campo **Categoria** é usado para definir como os encargos são calculados. Por exemplo, se os clientes precisarem cobrar uma taxa fixa de US$ 9,95 para que uma ordem seja enviada por um modo de entrega específico, use a categoria **Fixo** . Se a empresa decide cobrar os clientes um percentual do total da ordem para os encargos de entrega, use a categoria **Porcentagem** . O encargo real para os clientes é definido no campo **Valor dos encargos**.

As empresas frequentemente configuram encargos diferenciados. Nesse caso, o valor que os clientes pagam pela entrega é baseado no valor da ordem. Para configurar os encargos diferenciados, insira os valores nos campos **Valor de origem** e **Valor de destino** além de definir o próprio encargo no campo **Valor dos encargos**. Por exemplo, para ordens com um valor menor que US$ 50, um varejista cobra US$ 5,95 pelo frete terrestre. Para ordens que tenham um valor igual ou maior que US$ 50, mas menos que US$100, o varejista cobra US$7, 95. Finalmente, para ordens que tenham um valor igual ou maior que US$ 100, o varejista fornece frete grátis. A ilustração a seguir mostra a configuração desses encargos.

![Exemplo de encargos diferenciados fixos](media/fixedtieredcharges.png)

Você pode usar uma mistura de categorias para encargos, dependendo das suas necessidades comerciais. Por exemplo, para ordens com um valor menor que US$ 100, há um encargo fixo de US$ 9,95 para frete. Em seguida, para ordens que tenham um valor que é igual ou maior de US$ 100, encargos de entrega são calculadas a uma taxa de 5 por cento do valor da ordem. A ilustração a seguir mostra a configuração desses encargos.

![Exemplo de encargos diferenciados fixos](media/mixedtieredcharges.png)

## <a name="apply-delivery-modes-during-order-entry-in-a-call-center"></a>Aplicar modos de entrega durante a entrada de ordem em um call center

Quando uma nova ordem de venda é criada, o valor deve ser especificado no campo **Modo de entrega** na guia rápida **Entrega** do cabeçalho da ordem de venda. Este campo poderá ser preenchido automaticamente, com base nos valores padrão do registro de cliente.

O modo de entrega que é definido no cabeçalho da ordem será automaticamente copiado para as linhas de ordem de venda quando são criados. Entretanto, você pode alterar o modo de entrega de uma linha de item específica na guia **Entrega** na seção **Detalhes da linha** da página de entrada de ordem.

Se o modo de entrega selecionado não for válido para produtos ou o endereço de entrega que será definido para a ordem ou linha de ordem, você receberá uma mensagem de erro. Você deve selecionar um modo de entrega definido para suportar esse produto ou configuração de endereço.

## <a name="calculation-of-delivery-charges-during-entry-of-order"></a>Cálculo de taxas de entrega durante a entrada de ordem

Se a configuração **Habilitar conclusão de ordem** estiver ativada para o canal de call center, os encargos de remessa serão calculados automaticamente para ordens de venda quando os usuários selecionarem **Concluir**. A seguinte mensagem aparecerá na parte superior da página **Resumo da ordem de venda**: Encargos diferenciados calculados”. Os encargos calculados são adicionados ao valor do campo **Total de vendas** . Na guia rápida **Valor**, o campo **Encargos** mostra o valor total de todos os encargos calculados para a ordem e as linhas. Para ver uma análise mais detalhada das cobranças, selecione **Ordem** na página **Resumo da ordem de venda** e selecione a opção **Encargos** para exibir, adicionar ou editar os encargos. Observe que o cálculo de encargos de entrega no cabeçalho da ordem está baseado no modo de entrega que está vinculado ao cabeçalho. Os encargos de entrega no nível da linha são calculados com base no modo de entrega configurado para a linha de vendas. Se vários modos de entrega foram usados em linhas diferentes, vários encargos podem ser aplicados e adicionados juntos. O valor total é mostrado no campo **Encargos** na página **Resumo da ordem de venda** .

Se a configuração **Habilitar conclusão de ordem** for desativada, os usuários devem acionar manualmente o cálculo de encargos. Na página **Ordem de venda**, no Painel Ação, na guia **Vender**, no grupo **Calcular**, selecione **Encargos diferenciados**. A mensagem "Encargos diferenciados calculados" é exibida. Você pode selecionar a opção **Encargos** na guia **Vender** para exibir, editar ou excluir os encargos calculados.

## <a name="use-expedited-delivery-modes-on-call-center-orders"></a>Use modos de entrega expedidos em ordens do call center

Você também pode vincular um código de expedição a qualquer modo de entrega que você configurar. Esse código é usado como uma ferramenta de classificação e geração de relatórios de priorização. Atualmente, não é cobrada uma taxa adicional à ordem. Para configurar códigos de remessa, vá para **Vendas e marketing \> Configuração \> Distribuição \> Códigos de agilização**.

Por exemplo, para ordens que serão enviadas pelo ar no dia seguinte, a separação deverá ser feita no depósito às 13h todos os dias. Neste caso, um código de expedição pode ser criado, e o código pode ser vinculado no dia seguinte ao modo de entrega que é configurado no sistema. Quando o depósito criar sua onda de separação, o código de expedição apropriado no campo **Expedir** pode ser usado como filtro, de forma que a separação seja executada somente para ordens que tenham os modos de entrega vinculados ao código.

Além disso, quando uma ordem de call center é inserida, um código de expedição pode ser aplicado manualmente ao cabeçalho de ordem de venda ou linha de ordem de venda individual. Novamente, o código pode ser usado para fins de classificação ou relatório. Às vezes, uma ordem deve ser tratada cuidadosamente devido a uma emissão de serviço do cliente. Neste caso, um código de expedição específico pode ser aplicado ao cabeçalho ou a linhas de ordem para ajudar a identificar e priorizar a ordem durante o processo de atendimento.


[!INCLUDE[footer-include](../includes/footer-banner.md)]