---
title: Processamento de produtos de peso variável com gerenciamento de depósito
description: Este tópico descreve como usar modelos de trabalho e diretivas de localização para determinar como e onde o trabalho é realizado no depósito.
author: perlynne
ms.date: 08/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSCatchWeightTag, WHSCatchWeightItemHandlingPolicy, TMSLoadBuildWorkbench, WHSCatchWeightTagRegistration, WHSCatchWeightTagFullDimDiscrepancies, WHSCatchWeightTagChangeWeightDropDownDialog, WHSCatchWeightLinkWorkLineTagDropDownDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-1-31
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 8e56688aac445b84d5a9c0df289d48ffefd5767f673f2329f69582e820c27820
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738140"
---
# <a name="catch-weight-product-processing-with-warehouse-management"></a>Processamento de produtos de peso variável com gerenciamento de depósito

[!include [banner](../includes/banner.md)]

## <a name="feature-exposure"></a>Exposição de recurso

Para usar o gerenciamento de depósito para processar produtos de peso variável, você deve usar uma chave de configuração de licença para ativar a funcionalidade. Acesse **Administração de sistema \> Configurar \> Configuração de licença**. Em seguida, na guia **Chaves de configuração**, expanda **Comércio \> Gerenciamento de Depósito e Transporte** e marque a caixa de seleção para **Peso variável para depósito**.

> [!NOTE]
> Tanto a chave de configuração de licença de **Gerenciamento de Depósito e Transporte** quanto as chaves de configuração de licença de **Peso variável \> da distribuição de processos** também devem ser ativadas. Para definir as chaves de configuração para peso variável, você também deve ativar o recurso usando o espaço de trabalho **Gerenciamento de recursos**. O principal recurso que deve ser ativado é **Processamento de produtos de peso variável com gerenciamento de depósito**. Dois recursos relacionados, mas opcionais, que talvez você queira ativar são **Alterações de status de estoque para produtos de peso variável** e **Usar as marcas de peso variável existentes ao relatar ordens de produção como concluídas**.

Depois que a chave de configuração de licença está ativada, ao criar um produto liberado, você pode selecionar **Peso variável**. Você também pode associar o produto liberado a um grupo de dimensões de armazenamento para o qual o parâmetro **Usar processos de gerenciamento de depósito** foi selecionado.

Para usar o produto no Gerenciamento de depósito, você deve fazer algumas configurações básicas específicas do produto relativas a peso variável:

- Defina a conversão de peso nominal entre a unidade de peso variável (caixa) e a unidade de estoque (quilograma \[kg\]) como parte de uma definição de conversão de unidade.
- Defina as tolerâncias de peso mínimo e máximo como parte da configuração da unidade de peso variável.
- Configure um grupo de sequências de unidade em que a unidade de peso variável seja definida como a menor unidade de manutenção de estoque (SKU).
- Configure uma política de manuseio de itens de peso variável.

Para obter mais informações, consulte [Configurando e mantendo itens de peso variável](/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-catch-weight-items).

## <a name="transaction-adjustments"></a>Ajustes de transação

Como o peso do estoque quando dá entrada em um depósito pode diferir do peso ao sair do depósito, o processamento de produtos de peso variável deve ajustar o estoque.

> [!NOTE]
> A atividade do dispositivo móvel só irá disparar os ajustes de transação se o método de saída de variação de peso da política de manuseio de itens de peso variável do item for **Permitir variação de peso**.

### <a name="example-1"></a>Exemplo 1

Durante o processo de produção **Relatar como concluído**, o peso de entrada de uma placa de licença contendo oito caixas de um produto de peso variável é capturado como 80,1 kg. A placa de licença é armazenada na área de mercadorias acabadas e, durante o período de armazenamento, há uma perda de peso.

Posteriormente, como parte de um processo de separação de ordens de venda, o peso da mesma placa de licença é capturado como 79,8 kg. Portanto, no sistema, agora você tem uma diferença de peso como parte da dimensão física definida.

Nesse caso, o sistema ajusta a diferença automaticamente lançando uma transação relativa aos 300 gramas perdidos.

### <a name="example-2"></a>Exemplo 2

Em sua definição, um produto é configurado para tolerar um peso mínimo de 8 kg e um peso máximo de 12 kg para a unidade de peso variável **Caixa**.

Você tem duas caixas do produto, e elas têm um peso registrado de 16 kg. Se um funcionário do depósito escolher e pesar uma das caixas, e o peso capturado for de 9 kg, a caixa restante pesará 7 kg. Porém, como 7 kg está abaixo do peso mínimo, o sistema faz um ajuste automático para aumentar o peso do estoque disponível em 1 kg.

Para configurar as contas nas quais esses ajustes são lançados, Acesse **Gerenciamento de custos \> Configuração das políticas de integração do razão \> Lançamento**. Depois, na guia **Estoque**, defina as seguintes contas:

- Conta de perda de peso variável
- Conta de lucro de peso variável

## <a name="catch-weight-item-handling-policy"></a>Política de manuseio de itens de peso variável

A política de manuseio de itens de peso variável define dois fluxos principais de gerenciamento de depósito para os itens: quando e como o peso é capturado.

Você pode definir quando o peso é capturado para processamento de ordens de venda e de transferência. O peso pode ser capturado em qualquer um dos seguintes processos:

- **Separação** – o peso é capturado durante a separação inicial das linhas nas ordens de trabalho.
- **Embalagem** – o peso é capturado durante a embalagem manual. (Você deve enviar os itens a uma estação de embalagem.)

Se o peso real é capturado na estação de embalagem durante os processos de embalagem em contêiner, os funcionários do depósito não precisam capturar o peso durante o trabalho de separação. Em vez disso, o peso médio do estoque físico é usado como peso do estoque separado que vai para área de embalagem. Esse conceito também se aplica a itens de peso variável que são rastreados por marcas. Para itens rastreados por marca, esses parâmetros determinam quando a marca é capturada. A marca pode ser capturada no momento da separação usando o dispositivo móvel ou durante o empacotamento manual.

> [!NOTE]
> Como a opção **Embalagem** faz com que o estoque seja atualizado com o peso separado médio, isso pode acionar uma discrepância que pode causar um ajuste de lucros/perdas de peso variável e/ou uma diferença entre o peso do estoque disponível e o peso da marca de peso variável.

Para processos internos de gerenciamento de depósito, como correções de contagem e ajuste, você pode definir se o peso deve ser capturado. Se ele não é capturado, é usado o peso nominal. Outras opções permitem capturar o peso por unidade de peso variável e por quantidade de contagem.

Você também pode configurar como peso é capturado. Em um dos dois fluxos principais, marcas de peso variável são rastreadas e usadas para capturar o peso. No outro fluxo, as marcas de peso variável não são rastreadas.

- **Sim** – o item usa marcas de peso variável. Cada número de marca representa uma unidade de peso variável (caixa), e o peso e outras informações são associados à marca. Para os processos de saída, é usado o peso associado à marca.
- **Não** – o item não usa marcas de peso variável. Os processos de peso de entrada e de saída são baseados no peso real capturado durante cada processo.

O processo de rastrear marcas de peso variável pode ser usado para itens que não mudarão de peso durante o período de armazenamento. O peso será capturado somente durante o processo de entrada em depósito. No processo de saída, as marcas de peso variável apenas serão digitalizadas e os pesos associados a elas serão usados para o processamento da transação de saída.

Outro parâmetro importante relacionado ao processamento de marcas de peso variável é **Método de rastreamento de dimensão de marca de peso variável**. As marcas podem ser parcialmente rastreadas ou totalmente rastreadas. Se uma marca é parcialmente rastreada, ela rastreia dimensões do produto, dimensões de rastreamento e status do estoque. Se uma marca é totalmente rastreada, ela rastreia dimensões do produto, dimensões de rastreamento e **todas** as dimensões de armazenamento.

Além disso, quando um item é rastreado por marca, há um parâmetro **Método de captura de marca de saída**. Você pode definir este parâmetro para que você sempre seja solicitado a inserir a marca em transações de saída no dispositivo móvel. Como alternativa, você pode definir o parâmetro para ser solicitado a inserir as marcas somente quando elas forem necessárias. Por exemplo, há cinco marcas de peso variável no estoque em uma determinada placa de licença, e você indicou que quer separar todas as cinco marcas da placa de licença. Nesse caso, se o parâmetro **Método de captura de marca de saída** for definido como **Solicitar marca somente quando necessário**, as cinco marcas serão separadas automaticamente. Não é necessário verificar cada marca. Se o parâmetro for definido como **Sempre solicitar marca**, você deverá verificar cada marca, mesmo que todas as cinco marcas estejam sendo separadas.

> [!NOTE]
> Como regra, as marcas são capturadas e atualizadas somente dos itens de menu do dispositivo móvel. Contudo, existem alguns cenários em que as marcas são capturadas em outro local (por exemplo, na estação de embalagem manual). No entanto, em geral, os itens de menu do dispositivo móvel devem ser usados para todas as atividades de depósito se forem usadas marcas.

### <a name="how-to-capture-catch-weight"></a>Como capturar o peso variável

**Quando o rastreamento de marcas de peso variável é utilizado**, sempre deve ser criada uma marca para cada unidade de peso variável recebida, e cada marca sempre deve ser associada a um peso.

Por exemplo, **Caixa** é a unidade de peso variável, e você recebe um palete de oito caixas. Nesse caso, devem ser criadas oito marcas de peso variável exclusivas e um peso deve ser associado a cada uma delas. Dependendo da marca de peso variável de entrada, o peso de todas as oito caixas poderá ser capturado e o peso médio poderá ser distribuído para cada caixa ou um peso único poderá ser capturado para cada caixa.
Ao usar o recurso **Usar as marcas de peso variável existentes ao relatar ordens de produção como concluídas** com o processo habilitado por meio de um item de menu do dispositivo móvel, o inventário é atualizado com base nas informações existentes da marca de peso variável. Consequentemente, o aplicativo móvel do Gerenciamento de Depósito não solicita a captura dos dados da marca de peso variável como parte de um relatório de produção como uma operação finalizada.

**Quando o rastreamento de marcas de peso variável não é usado**, é possível capturar o peso para cada conjunto de dimensões (por exemplo, para cada placa de licença e dimensão de rastreamento). Como alternativa, o peso pode ser capturado com base em um nível agregado, como cinco placas de licença (paletes).

Para os métodos de captura de peso de saída, a opção **Por unidade de peso variável** permite especificar que a pesagem deve ser feita para cada unidade de peso variável (por exemplo, por caixa). A opção **Por unidade de separação** permite especificar que o peso deve ser capturado com base na quantidade que será separada (por exemplo, três caixas). Observe que, para os processos de separação de linha de produção e movimentação interna, o peso médio será usado se a opção **Não capturado** for usada.

Vários métodos de captura de peso são definidos na política de manuseio de itens de peso variável. Cada parâmetro do método de captura de peso é usado por várias transações. A tabela a seguir resume quais parâmetros são usados por quais transações.

| Método                                     | Transação                                |
|--------------------------------------------|--------------------------------------------|
| Método de captura de peso de saída           | Separação de venda, Separação de transferência            |
| Método de captura de peso da separação de produção | Separação de produção, Consumo de produção |
| Método de captura de peso do movimento           | Movimentação                                   |
| Quando capturar a correção do peso       | Ajustes, Contagem                      |
| Método de captura da contagem de peso           | Contando                                   |
| Método de captura da transferência de peso do depósito | Transferência de depósito                         |

Para impedir que os processos de separação do gerenciamento de depósito capturem pesos que resultem em ajustes de lucros/perdas de peso variável, você pode usar o método de saída de variação de peso. O método de saída de variação de peso aplica-se durante os seguintes processos do dispositivo móvel: separação de venda, separação de transferência, separação de produção, movimentações, contagem e transferências de depósito. Você poderá usar a opção **Restringir a variação de peso** se o peso do item de peso variável não for flutuante durante o armazenamento no depósito e se ajustes de lucros/perdas de peso variável não forem necessários. Você poderá usar a opção **Permitir variação de peso** se o peso puder flutuar e se forem necessários ajustes de lucros/perdas de peso variável quando uma flutuação de peso for registrada.

## <a name="unsupported-scenarios"></a>Cenários sem suporte

Nem todos os fluxos de trabalho dão suporte ao processamento de produtos de peso variável com o gerenciamento de depósito. No momento, as limitações a seguir se aplicam. Elas se aplicam a todos os itens de peso variável, independentemente de estarem marcados.

### <a name="configuring-catch-weight-products-for-warehouse-management-processes"></a>Configuração de produtos de peso variável para processos de gerenciamento de depósito

- Somente o processamento de fórmulas é suportado para produtos de peso variável (não para a lista de materiais).
- Os produtos de peso variável não podem ser associados a um grupo de dimensões de rastreamento usando a dimensão Proprietário.
- Os produtos de peso variável não podem ser usados como serviços.
- Os produtos de peso variável podem ser usados como “produtos em estoque” somente como parte do grupo de modelos de item.
- Os produtos de peso variável não podem ser usados com a funcionalidade para rastrear “Ativo no processo de venda”.
- Os produtos de peso variável não podem ser usados com a funcionalidade para capturar números de série. Por isso não é possível transferir os produtos de “em branco” para um número de série como parte do processo de separação/embalagem.
- Os produtos de peso variável não podem ser usados com a funcionalidade para registrar números de série antes do consumo.
- Os produtos de peso variável habilitados para variante não podem ser usados com a funcionalidade para converter unidades de medida variantes.
- Não é possível marcar produtos de peso variável como um "kit de produto" de comércio.
- Os produtos de peso variável podem ser usados apenas com um grupo de sequências de unidade que tem unidades de manuseio de material de peso variável e que tem a unidade de peso variável como a sequência mais baixa.
- Para produtos de peso variável, a unidade de estoque pode ser convertida na unidade de peso variável somente quando a conversão gera uma quantidade nominal maior que 1.
- A configuração de códigos de barras para produtos de peso variável não suporta uma configuração de peso variável.

### <a name="order-processing"></a>Processamento de ordens

- A criação do aviso de embarque (ASN/estruturas de embalagem) não oferece suporte para informações de peso.
- A quantidade da ordem deve ser mantida com base na unidade de peso variável.

### <a name="inbound-warehouse-processing"></a>Processamento de depósito de entrada

- Para receber placas de licença. é preciso que os pesos sejam atribuídos durante o registro, pois as informações de peso não têm suporte como parte do aviso de embarque. Quando processos de marca de peso variável são usados, o número da marca deve ser atribuído manualmente por unidade de peso variável.
- O trabalho de verificação de qualidade de entrada não tem suporte para produtos de peso variável. Se configurado, o trabalho de verificação de qualidade será ignorado.

### <a name="inventory-and-warehouse-operations"></a>Operações de estoque e depósito

- A criação manual de ordens de quarentena não tem suporte para produtos de peso variável.
- A movimentação manual de estoque relacionada ao trabalho aberto não tem suporte para produtos de peso variável.
- A carga da placa de licenças para inicializar o estoque de depósito não tem suporte para produtos de peso variável.
- Processos de balanceamento de lote não têm suporte para produto de peso variável.
- O manuseio de estoque físico negativo não tem suporte para produtos de peso variável.
- A marcação de estoque não pode ser usada para produtos de peso variável.

### <a name="outbound-warehouse-processing"></a>Processamento de depósito de saída

- A funcionalidade de separação de cluster não tem suporte para produtos de peso variável.
- O processamento do depósito de separação e embalagem não tem suporte para produtos de peso variável.
- Para produtos de peso variável, o trabalho definido em um modelo de trabalho não pode ser executado automaticamente.
- Para produtos de peso variável, o sistema não oferece suporte para o processamento manual da estação de embalagem onde o trabalho de separação de contêineres embalados é criado após o fechamento dos contêineres.
- A funcionalidade de verificação pcs por pcs não tem suporte para produtos de peso variável.

### <a name="production-processing"></a>Processamento de produção

- Para produtos de peso variável, apenas ordens de lote para produtos de fórmula têm suporte.
- A funcionalidade kanban não tem suporte para produtos de peso variável.
- Para produtos de peso variável, não é possível registrar os números de série antes do consumo.
- A funcionalidade de reversão de placas de licença de produção não tem suporte para produtos de peso variável.
- Para produtos de peso variável, não é possível registrar por número de série os produtos relatados como concluídos.

### <a name="transportation-management-processing"></a>Processamento de gerenciamento de transporte

- O processamento da bancada de criação de carga não tem suporte para produtos de peso variável.
- As linhas de solicitação de transporte não têm suporte para produtos de peso variável.

### <a name="other-restrictions-and-behaviors-for-catch-weight-product-processing-with-warehouse-management"></a>Outras restrições e comportamentos para o processamento de produtos de peso variável com gerenciamento de depósito

- Durante os processos de separação nos quais o usuário não é solicitado a identificar dimensões de rastreamento, a atribuição de peso é feita com base no peso médio. Esse comportamento ocorre quando, por exemplo, uma combinação de dimensões de rastreamento é usada no mesmo local e, depois que um usuário processa a separação, somente um valor de dimensão de rastreamento permanece no local.
- Quando o estoque é reservado para um produto de peso variável configurado para processos de gerenciamento de depósito, a reserva é feita com base no peso mínimo definido, mesmo se essa quantidade for a última quantidade de manuseio disponível. Esse comportamento difere do comportamento de itens que não estão configurados para processos de gerenciamento de depósito. Há uma exceção a essa restrição. Para a separação de produção, quando a última quantidade de manuseio de um produto de peso variável controlado por número de série é separada, o peso real é usado.
- Os processos que usam o peso como parte dos cálculos de capacidade (limites de onda, máximo de divisões de trabalho, máximos de contêineres, capacidades de carga da localização, entre outros) não usam o peso real do estoque. Em vez disso, os processos são baseados no peso de manuseio físico definido para o produto.
- De forma geral, a funcionalidade de comércio não tem suporte para produtos de peso variável.
- Para produtos de peso variável, o status de estoque não pode ser atualizado em **Alteração de status do depósito**.

### <a name="catch-weight-tags"></a>Marcas de peso variável

Uma marca de peso variável pode ser criada usando um processo de aplicativo móvel do Gerenciamento de Depósito, criada manualmente no formulário **Gerenciamento de depósito > Consultas e relatórios > Marca de peso variável** ou pode ser criada usando um processo de entidade de dados. Se a etiqueta de peso variável for associada a uma linha do documentos de origem de entrada, como a linha de ordem de compra, a marca será registrada. Se a linha for usada para processamento de saída, a marca será atualizada como remetida. Você pode exibir todos os eventos de registro de marca de peso variável por meio da opção **Registro de marca de peso variável** na página **Marca de peso variável**.

Você pode usar a opção **Alterar peso capturado da marca** para atualizar manualmente o valor de peso de uma marca de peso variável. Observe que o peso para o estoque disponível não será ajustado como parte desse processo manual, mas você poderá usar facilmente a página **Discrepâncias disponíveis para itens marcados em peso variável** para procurar as discrepâncias entre as marcas de peso variável ativas no momento e o estoque atual.

Outras opções manuais são **Registrar a marca** em uma linha do documento de origem e **Registrar o trabalho** em um depósito existente.

Além das restrições que se aplicam no momento a produtos de peso variável, os produtos de peso variável marcados têm outras restrições aplicáveis.

- Todas as atualizações manuais do estoque (ou seja, as que não são feitas usando um dispositivo móvel) devem incluir as atualizações manuais correspondentes nas marcas de peso variável associadas, pois estas não são feitas de maneira automática. Por exemplo, os diários de ajuste manual atualizarão o estoque, mas não as marcas de peso variável associadas.
- Você deve atualizar manualmente as marcas de peso variável para refletir as movimentações de trabalho de reabastecimento. Isso ocorre porque o sistema não pode capturar pesos enquanto processa o trabalho de reabastecimento e, por isso, registra o peso médio.
- No momento, não há suporte para recebimento de placa de licença mista de itens peso variável marcados.
- O processamento do recebimento de ordens de devolução de venda pode registrar marcas de peso variável. No entanto, o processo não valida que a marca devolvida é a mesma que foi originalmente remetida para uma ordem de venda.
- No momento, o item de menu de dispositivo móvel que tem o código de atividade **Registrar consumo de material** não oferece suporte para o registro de marcas de peso variável.
- Apesar de haver suporte para os processos de contagem de itens de peso variável marcados, eles são limitados. Por exemplo, você pode usar as opções de dispositivo móvel para contar itens de peso variável marcados, e o peso médio é usado. Porém, as marcas de peso variável não são atualizadas automaticamente pela transação de contagem. Depois que a transação de contagem é concluída, as marcas de peso variável devem ser atualizadas manualmente para refletir o estoque. Se os itens que não estavam originalmente em um local forem contados nesse local, o peso nominal será usado.
- No momento, a consolidação de placas de licença não oferece suporte para itens de peso variável marcados.
- Não há suporte para a funcionalidade de reversão de trabalho para itens de peso variável que são rastreados pelo número da marca.

> [!NOTE]
> As informações anteriores sobre marcas de peso variável só são válidas se o produto de peso variável tem um método de rastreamento de dimensão de marca de peso variável que é totalmente rastreado (ou seja, se o parâmetro **Método de rastreamento de dimensão de marca de peso variável** na política de manuseio de itens de peso variável está definido como **Dimensões do produto, dimensões de rastreamento e todas as dimensões de armazenamento**). Se o item de peso variável só é parcialmente rastreado por marca (ou seja, se o parâmetro **Método de rastreamento de dimensão de marca de peso variável** na política de manuseio de itens de peso variável estiver definido como **Dimensões do produto, dimensões de rastreamento e status de estoque**), outras restrições são aplicadas. Como nesse caso a visibilidade é perdida entre a marca e o estoque, não há suporte para alguns cenários adicionais.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]