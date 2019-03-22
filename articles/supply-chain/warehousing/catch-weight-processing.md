---
title: Processamento de produtos de peso variável com gerenciamento de depósito
description: Este tópico descreve como usar modelos de trabalho e diretivas de localização para determinar como e onde o trabalho é realizado no depósito.
author: perlynne
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCatchWeightTag, WHSCatchWeightItemHandlingPolicy
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-1-31
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: ced22a144e57b624ceacb8bb5c3032218db3a0eb
ms.sourcegitcommit: bacec397ee48ac583596be156c87ead474ee07df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2019
ms.locfileid: "777263"
---
# <a name="catch-weight-product-processing-with-warehouse-management"></a>Processamento de produtos de peso variável com gerenciamento de depósito

[!include [banner](../includes/banner.md)]

## <a name="feature-exposure"></a>Exposição de recurso

Para usar o gerenciamento de depósito para processar produtos de peso variável, você deve usar uma chave de configuração de licença para ativar a funcionalidade. (Vá para **Administração do sistema \> Configuração \> Configuração da licença**. Em seguida, na guia **Chaves de configuração**, expanda **Comércio \> Gerenciamento de Depósito e Transporte** e marque a caixa de seleção para **Peso variável para depósito**).

> [!NOTE]
> Tanto a chave de configuração de licença de **Gerenciamento de Depósito e Transporte** quanto as chaves de configuração de licença de **Peso variável \> da distribuição de processos** também devem ser ativadas.

Depois que a chave de configuração de licença está ativada, ao criar um produto liberado, você pode selecionar **Peso variável**. Você também pode associar o produto liberado a um grupo de dimensões de armazenamento para o qual o parâmetro **Usar processos de gerenciamento de depósito** foi selecionado.

Para usar o produto no Gerenciamento de depósito, você deve fazer algumas configurações básicas específicas do produto relativas a peso variável:

- Defina a conversão de peso nominal entre a unidade de peso variável (caixa) e a unidade de estoque (quilograma \[kg\]) como parte de uma definição de conversão de unidade.
- Defina as tolerâncias de peso mínimo e máximo como parte da configuração da unidade de peso variável.
- Configure um grupo de sequências de unidade em que a unidade de peso variável seja definida como a menor unidade de manutenção de estoque (SKU).
- Configure uma política de manuseio de itens de peso variável.

Para obter mais informações, consulte [Configurando e mantendo itens de peso variável](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-catch-weight-items).

## <a name="transaction-adjustments"></a>Ajustes de transação

Como o peso do estoque quando dá entrada em um depósito pode diferir do peso ao sair do depósito, o processamento de produtos de peso variável deve ajustar o estoque.

**Exemplo 1**

Durante o processo de produção **Relatar como concluído**, o peso de entrada de uma placa de licença contendo oito caixas de um produto de peso variável é capturado como 80,1 kg. A placa de licença é armazenada na área de mercadorias acabadas e, durante o período de armazenamento, há uma perda de peso.

Posteriormente, como parte de um processo de separação de ordens de venda, o peso da mesma placa de licença é capturado como 79,8 kg. Portanto, no sistema, agora você tem uma diferença de peso como parte da dimensão física definida.

Nesse caso, o sistema ajusta a diferença automaticamente lançando uma transação relativa aos 300 gramas perdidos.

**Exemplo 2**

Em sua definição, um produto é configurado para tolerar um peso mínimo de 8 kg e um peso máximo de 12 kg para a unidade de peso variável **Caixa**.

Você tem duas caixas do produto, e elas têm um peso registrado de 16 kg. Se um funcionário do depósito escolher e pesar uma das caixas, e o peso capturado for de 9 kg, a caixa restante pesará 7 kg. Porém, como 7 kg está abaixo do peso mínimo, o sistema faz um ajuste automático para aumentar o peso do estoque disponível em 1 kg.

Para configurar as contas nas quais esses ajustes são lançados, vá para **Gerenciamento de custos \> Configuração das políticas de integração do razão \> Lançamento**. Depois, na guia **Estoque**, defina as seguintes contas:

- Conta de perda de peso variável
- Conta de lucro de peso variável

## <a name="catch-weight-item-handling-policy"></a>Política de manuseio de itens de peso variável

A política de manuseio de itens de peso variável define dois fluxos principais de gerenciamento de depósito para os itens: quando e como o peso é capturado.

Você pode definir quando o peso é capturado para processamento de ordens de venda e de transferência. O peso pode ser capturado em qualquer um dos seguintes processos:

- **Separação** – o peso é capturado durante a separação inicial das linhas nas ordens de trabalho.
- **Embalagem** – o peso é capturado durante a embalagem manual. (Você deve enviar os itens a uma estação de embalagem.)

Se o peso real é capturado na estação de embalagem durante os processos de embalagem em contêiner, os funcionários do depósito não terão de capturar o peso durante o trabalho de separação. Em vez disso, o peso médio do estoque físico será usado como o peso do estoque separado que vai para área de embalagem.

Para processos internos de gerenciamento de depósito, como correções de ajuste e contagem, é possível definir se o peso deve ou não ser capturado. Se não for capturado, será usado o peso nominal.

Você também pode configurar como peso é capturado. Em um dos dois fluxos principais, marcas de peso variável são rastreadas e usadas para capturar o peso. No outro fluxo, as marcas de peso variável não são rastreadas.

- **Sim** – o item usa marcas de peso variável. Cada número de marca representa uma unidade de peso variável (caixa), e o peso e outras informações são associados à marca. Para os processos de saída, é usado o peso associado à marca.
- **Não** – o item não usa marcas de peso variável. Os processos de peso de entrada e de saída são baseados no peso real capturado durante cada processo.

O processo de rastrear marcas de peso variável pode ser usado para itens que não mudarão de peso durante o período de armazenamento. O peso será capturado somente durante o processo de entrada em depósito. No processo de saída, as marcas de peso variável apenas serão digitalizadas e os pesos associados a elas serão usados para o processamento da transação de saída.

### <a name="how-to-capture-catch-weight"></a>Como capturar o peso variável

Quando o rastreamento de marcas de peso variável é utilizado, sempre deve ser criada uma marca para cada unidade de peso variável recebida, e cada marca sempre deve ser associada a um peso.

Por exemplo, **Caixa** é a unidade de peso variável, e você recebe um palete de oito caixas. Nesse caso, devem ser criadas oito marcas de peso variável exclusivas e um peso deve ser associado a cada uma delas. Dependendo da marca de peso variável de entrada, o peso de todas as oito caixas poderá ser capturado e o peso médio poderá ser distribuído para cada caixa ou um peso único poderá ser capturado para cada caixa.

Quando o rastreamento de marcas de peso variável não é usado, é possível capturar o peso para cada dimensão definida (por exemplo, para cada placa de licença e dimensão de rastreamento.) Como alternativa, o peso pode ser capturado com base em um nível agregado, como cinco placas de licença (paletes).

Quanto aos métodos para capturar o peso de saída, é possível definir se a pesagem é feita para cada unidade de peso variável (isto é, por caixa) ou se o peso é capturado com base na quantidade a ser separada (por exemplo, três caixas). Lembre-se de que, para o processo de separação de linha de produção, o peso médio será usado se a opção **Não capturado** for escolhida.

## <a name="supported-scenarios"></a>Cenários com suporte

Nem todos os fluxos de trabalho dão suporte ao processamento de produtos de peso variável com o gerenciamento de depósito. No momento, as limitações a seguir se aplicam.
 
### <a name="configuring-catch-weight-products-for-warehouse-management-processes"></a>Configuração de produtos de peso variável para processos de gerenciamento de depósito

- Para produtos de peso variável, o grupo de dimensões de armazenamento para itens não pode ser alterado (de forma que os processos de gerenciamento de depósitos possam ser usados para eles.)
- Somente o processamento de fórmulas é suportado para produtos de peso variável (não para a lista de materiais).
- Os produtos de peso variável não podem ser associados a um grupo de dimensões de rastreamento usando a dimensão Proprietário.
- Os produtos de peso variável não podem ser usados como serviços.
- Os produtos de peso variável podem ser usados como “produtos em estoque” somente como parte do grupo de modelos de item.
- Os produtos de peso variável não podem ser usados com a funcionalidade para rastrear “Ativo no processo de venda”.
- Os produtos de peso variável não podem ser usados com a funcionalidade para capturar números de série. Por isso não é possível transferir os produtos de “em branco” para um número de série como parte do processo de separação/embalagem.
- Os produtos de peso variável não podem ser usados com a funcionalidade para registrar números de série antes do consumo.
- Os produtos de peso variável habilitados para variante não podem ser usados com a funcionalidade para converter unidades de medida variantes.
- Não é possível marcar produtos de peso variável como um "kit de produto" de varejo.
- Os produtos de peso variável podem ser usados apenas com um grupo de sequências de unidade que tem unidades de manuseio de material de peso variável e que tem a unidade de peso variável como a sequência mais baixa.
- Para produtos de peso variável, a unidade de estoque pode ser convertida na unidade de peso variável somente quando a conversão gera uma quantidade nominal maior que 1.
- A configuração de códigos de barras para produtos de peso variável não suporta uma configuração de peso variável.
 
### <a name="order-processing"></a>Processamento de ordens

- O processamento de ordens intercompanhia não tem suporte.
- A criação do aviso de embarque (ASN/estruturas de embalagem) não oferece suporte para informações de peso.
- A quantidade da ordem deve ser mantida com base na unidade de peso variável.
 
### <a name="inbound-warehouse-processing"></a>Processamento de depósito de entrada

- Para receber placas de licença. é preciso que os pesos sejam atribuídos durante o registro, pois as informações de peso não têm suporte como parte do aviso de embarque. Quando processos de marca de peso variável são usados, o número da marca deve ser atribuído manualmente por unidade de peso variável.
- O recebimento de placas de licença mistas não tem suporte para produtos de peso variável.
 
### <a name="inventory-and-warehouse-operations"></a>Operações de estoque e depósito

- A criação manual de ordens de quarentena não tem suporte para produtos de peso variável.
- A movimentação manual de estoque relacionado ao trabalho não tem suporte para produtos de peso variável.
- A consolidação de placas de licença não tem suporte para produtos de peso variável.
- Não há suporte para alterações no status de estoque do depósito como parte de uma tarefa periódica para produtos de peso variável.
- Não há suporte para alterações no status do estoque definidas por uma consulta para produtos de peso variável. (Também não há suporte para alterações no status do estoque da ordem de qualidade.)
- Para produtos de peso variável, o status do estoque não pode ser alterado da página **Disponibilidade por localização**.
- Para produtos de peso variável, o status do estoque não pode ser alterado como parte do trabalho de movimentação do app de depósito.
- A carga da placa de licenças para inicializar o estoque de depósito não tem suporte para produtos de peso variável.
- Processos de balanceamento de lote não têm suporte para produto de peso variável.
- O manuseio de estoque físico negativo não tem suporte para produtos de peso variável.
- A marcação de estoque não pode ser usada para produtos de peso variável.
 
### <a name="outbound-warehouse-processing"></a>Processamento de depósito de saída

- A funcionalidade de separação de cluster não tem suporte para produtos de peso variável.
- O processamento do depósito de separação e embalagem não tem suporte para produtos de peso variável.
- Para produtos de peso variável, o trabalho não pode ser concluído na página **Trabalho** .
- Para produtos de peso variável, o trabalho definido em um modelo de trabalho pode ser executado automaticamente.
- A funcionalidade de trabalho de reversão não tem suporte para produtos de peso variável.
- Para produtos de peso variável, não há suporte para o processamento manual da estação de embalagem onde o trabalho é criado após o fechamento dos contêineres.
- A funcionalidade de verificação pcs por pcs não tem suporte para produtos de peso variável.
 
### <a name="production-processing"></a>Processamento de produção

- Para produtos de peso variável, apenas ordens de lote para produtos de fórmula têm suporte.
- A funcionalidade kanban não tem suporte para produtos de peso variável.
- Para produtos de peso variável, não é possível registrar os números de série antes do consumo.
- A funcionalidade de reversão de placas de licença não tem suporte para produtos de peso variável.
- Para produtos de peso variável, é possível registrar por número de série os produtos relatados como concluídos.

### <a name="transportation-management-processing"></a>Processamento de gerenciamento de transporte

- O processamento da bancada de criação de carga não tem suporte para produtos de peso variável.
- As linhas de solicitação de transporte não têm suporte para produtos de peso variável.
 
### <a name="other-restrictions-and-behaviors-for-catch-weight-product-processing-with-warehouse-management"></a>Outras restrições e comportamentos para o processamento de produtos de peso variável com gerenciamento de depósito

- Quando as marcas de peso variável são capturadas como parte do processamento do app de depósito, o usuário não pode cancelar o fluxo de trabalho.
- Durante os processos de separação nos quais o usuário não é solicitado a identificar dimensões de rastreamento, a atribuição de peso é feita com base no peso médio. Esse comportamento ocorre quando, por exemplo, uma combinação de dimensões de rastreamento é usada no mesmo local e, depois que um usuário processa a separação, somente um valor de dimensão de rastreamento permanece no local.
- Quando o estoque é reservado para um produto de peso variável configurado para processos de gerenciamento de depósito, a reserva é feita com base no peso mínimo definido, mesmo se essa quantidade for a última quantidade de manuseio disponível. Esse comportamento difere do comportamento de itens que não estão configurados para processos de gerenciamento de depósito.
- Os processos que usam o peso como parte dos cálculos de capacidade (limites de onda, máximo de divisões de trabalho, máximos de contêineres, capacidades de carga da localização, entre outros) não usam o peso real do estoque. Em vez disso, os processos são baseados no peso de manuseio físico definido para o produto.
- De forma geral, a funcionalidade de varejo não tem suporte para produtos de peso variável.
 
### <a name="catch-weight-tags"></a>Marcas de peso variável

No momento, a funcionalidade de marcas de peso variável tem suporte apenas como parte dos seguintes cenários:

- Ao processar o recebimento de ordens de compra pelo app de depósito.
- Ao processar o recebimento de cargas pelo app de depósito.
- Para o recebimento de placas de licença relacionado a uma carga de ordem de compra, a atribuição de peso é solicitada durante o processo de recebimento. Por outro lado, para o recebimento de ordens de transferência, é usado o peso dos dados de remessa da ordem de transferência.
- Para o recebimento de linhas e itens de ordens de transferência provenientes de um depósito de processos não de gerenciamento de depósito.
- O processamento do recebimento de ordens de devolução de venda pode registrar marcas de peso variável, mas ele não será validado se as marcas forem iguais às enviadas originalmente para uma determinada linha da ordem de venda.
- Ao processar um status de estoque que foi alterado usando o app de depósito.
- Quando uma transferência de depósito é feita usando o app de depósito.
- Ao processar ajustes dentro e para do app de depósito.
- Quando o trabalho de separação é processado para ordens de venda e de transferência. (As marcas de peso variável não podem ser registradas para a separação de componentes de produção.)
- Quando as quantidades separadas são reduzidas das linhas de carga, independentemente do uso de contêineres.
- Quando os produtos são embalados em contêineres em uma estação de embalagem.
- Quando os contêineres são reabertos.
- Quando produtos de fórmula são relatados como concluídos usando o app de depósito.
- Quando cargas de transporte são processadas usando o app de depósito.
