---
title: Certificação de origem do USMCA
description: Este recurso permite imprimir os documentos de certificação de origem exigidos pelo Acordo Estados Unidos-México-Canadá (USMCA).
author: Weijiesa
ms.date: 10/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-10-23
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 9fed5f93441bbc29b039bd1562821b999a58e5e1
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8677580"
---
# <a name="usmca-certification-of-origin"></a>Certificação de origem do USMCA

[!include [banner](../includes/banner.md)]

Este recurso permite imprimir os documentos de certificação de origem exigidos pelo Acordo Estados Unidos-México-Canadá (USMCA).

O *documento de certificação de origem do USMCA* contém os elementos de dados mínimos exigidos para a declaração. Alguns elementos de dados podem ser preenchidos previamente antes da impressão, enquanto outros devem ser preenchidos manualmente após a impressão. Para obter tratamento tarifário preferencial, o documento deve estar preenchido e em posse do importador no momento da declaração. O documento pode ser preenchido pelo importador, exportador ou produtor.

É possível imprimir o documento para uma única remessa na página da lista **Todas as remessas** ou na página **Detalhes da remessa**.

O documento só pode ser acessado quando o país do endereço principal da entidade legal for os Estados Unidos.

Dependendo da seleção de impressão do documento, o documento pode ser preenchido previamente com dados do seu sistema. É possível alterar ou adicionar dados ao documento impresso, exportando o documento impresso para um formato editável, como o Microsoft Word. Após a exportação, você pode aplicar qualquer alteração necessária antes que uma declaração seja realizada.

## <a name="turn-on-the-usmca-feature"></a>Ativar o recurso do USMCA

Para que você possa usar o recurso do USMCA, ele deve estar ativado no sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Gerenciamento de transporte*
- **Nome do recurso:** *documento de certificação de origem do USMCA*

## <a name="document-content"></a>Conteúdo do documento

O documento de certificação de origem do USMCA contém os seguintes elementos de dados:

- Elementos de endereço
- Função da entidade certificadora
- Remessa única
- Faturas
- Período em aberto
- Detalhes do item
- Assinatura do certificador
- Número de páginas

Para obter mais informações sobre cada um desses elementos e como seus valores são encontrados, consulte as seções restantes deste tópico.

## <a name="print-a-usmca-certification-of-origin-document"></a>Imprimir um documento de certificação de origem do USMCA

Para imprimir um documento de certificação de origem do USMCA para uma remessa, faça o seguinte:

1. Execute um destes procedimentos:
    - Acesse **Gerenciamento de transporte > Remessas > Todas as remessas** e selecione a remessa em relação à qual deseja imprimir o documento.
    - Abra a página **Detalhes da remessa** da remessa em relação à qual deseja imprimir o documento (há várias maneiras de chegar aqui, incluindo a página **Todas as remessas**).
1. No Painel de Ações, abra a guia **Remessas** e, no grupo **Imprimir**, selecione **Certificação de origem do USMCA**.
1. A caixa de diálogo **Certificado ou origem** é aberta. Faça as configurações descritas nas subseções a seguir e selecione **OK** para gerar o documento.
1. Uma visualização do documento é aberta. Use os comandos fornecidos no Painel de Ações para imprimir ou exportar o documento conforme necessário.

### <a name="certifying-party"></a>Entidade certificadora

Use a lista suspensa **Entidade certificadora** para identificar o tipo de entidade que está imprimindo o documento. Especifique se a entidade certificadora é *Exportador*, *Exportador e produtor*, *Produtor* ou *Importador*; ou deixe em branco se nenhuma delas for a entidade certificadora. A opção selecionada determina o que é impresso nas seções de endereço do documento.

A **Entidade certificadora** que você escolher será incluída no documento impresso.

O documento pode ser impresso para remessas de entrada e saída. Selecione *Importador* como **Entidade certificadora** somente para remessas de entrada.

A tabela a seguir descreve os tipos de informações incluídos no documento com base na **Entidade certificadora** que você escolher.

| Entidade&nbsp;certificadora | descrição |
|---|---|
| *\[Em Branco\]* | Adiciona os seguintes detalhes ao documento:<ul><li>**Detalhes do certificador**: usa os detalhes do endereço do depósito de remessa, se disponível; caso contrário, usa o endereço do site de remessa, se disponível; caso contrário, usa o endereço da entidade legal (empresa) selecionada no Supply Chain Management.</li><li>**Detalhes do exportador**: em branco</li><li>**Detalhes do produtor**: em branco</li><li>**Detalhes do importador**: em branco</li><ul>|
| *Exportador* | Adiciona os seguintes detalhes ao documento:<ul><li>**Detalhes do certificador**: usa os detalhes do endereço do depósito de remessa, se disponível; caso contrário, usa o endereço do site de remessa, se disponível; caso contrário, usa o endereço da entidade legal (empresa) selecionada no Supply Chain Management.</li><li>**Detalhes do exportador**: usa os detalhes do endereço da entidade legal.</li><li>**Detalhes do produtor**: em branco</li><li>**Detalhes do importador**: usa a conta da fatura para a ordem de venda relacionada.</li><ul>|
| *Exportador e produtor* | Adiciona os seguintes detalhes ao documento:<ul><li>**Detalhes do certificador**: usa os detalhes do endereço do depósito de remessa, se disponível; caso contrário, usa o endereço do site de remessa, se disponível; caso contrário, usa o endereço da entidade legal (empresa) selecionada no Supply Chain Management.</li><li>**Detalhes do exportador**: usa os detalhes do endereço da entidade legal.</li><li>**Detalhes do produtor**: usa os detalhes do endereço da entidade legal.</li><li>**Detalhes do importador**: usa a conta da fatura para a ordem de venda relacionada.</li><ul>|
| *Importador* | Adiciona os seguintes detalhes ao documento:<ul><li>**Detalhes do certificador**: usa os detalhes do endereço do depósito de remessa, se disponível; caso contrário, usa o endereço do site de remessa, se disponível; caso contrário, usa o endereço da entidade legal (empresa) selecionada no Supply Chain Management.</li><li>**Detalhes do exportador**: em branco</li><li>**Detalhes do produtor**: em branco</li><li>**Detalhes do importador**: usa os detalhes do endereço da entidade legal.</li><ul>|
| *Produtor* | Adiciona os seguintes detalhes ao documento:<ul><li>**Detalhes do certificador**: usa os detalhes do endereço do depósito de remessa, se disponível; caso contrário, usa o endereço do site de remessa, se disponível; caso contrário, usa o endereço da entidade legal selecionada no Supply Chain Management.</li><li>**Detalhes do exportador**: em branco</li><li>**Detalhes do produtor**: usa os detalhes do endereço da entidade legal.</li><li>**Detalhes do importador**: em branco</li><ul>|

### <a name="has-various-producers"></a>Tem vários produtores

A lista suspensa **Entidade certificadora** controla o texto a ser usado para os detalhes do produtor no documento. Selecione uma das seguintes opções:

- *Vários produtores* - Imprime o texto "Vários" nos detalhes do produtor.
- *Disponível mediante solicitação* - Imprime o texto "Disponível mediante solicitação das autoridades de importação" nos dados do produtor.

Quando a **Entidade certificadora** é definida como *Exportador e produtor* ou *Produtor*, a configuração **Tem vários produtores** é anulada e os detalhes do endereço do produtor serão iguais aos do certificador.

### <a name="blanket-period"></a>Período em aberto

Use as configurações **Período de cobertura de** e **Período de cobertura até** para estabelecer um período amplo, durante o qual o documento cobrirá várias remessas de mercadorias idênticas, mesmo que o documento seja impresso para apenas uma remessa. Você pode definir as datas do período de cobertura sem qualquer restrição e elas serão adicionadas ao documento. Você também pode deixar essas configurações em branco ou defini-las no passado.

### <a name="is-single-shipment"></a>É uma única remessa

Na caixa de diálogo **Certificação de origem**, defina **É uma única remessa** para uma das seguintes opções:

- *Sim* - Adiciona "Remessa única: Sim" ao lado do número da fatura.
- *Não* - Não adiciona nada.

## <a name="other-information-included-in-the-document"></a>Outras informações incluídas no documento

Além dos elementos opcionais que você seleciona usando a caixa de diálogo **Certificado ou origem**, o documento de certificação de origem do USMCA incluirá as informações e os campos personalizados resumidos nas subseções a seguir. Algumas dessas informações devem ser inseridas manualmente após a geração do documento.

### <a name="invoice-number"></a>Número da fatura

As IDs de faturas de vendas relacionadas a remessas são impressos no documento, independentemente do período programado. Os números das faturas são impressos independentemente da seleção **É uma única remessa**.

### <a name="item-details"></a>Detalhes do item

O documento fornece várias seções que listam detalhes de itens específicos, que são:

- **Número SKU**: imprime o número do item do produto liberado.

- **Descrição**: imprime a descrição ou o nome do produto liberado. Se houver uma descrição no idioma do usuário, ela será impressa. Se essa descrição não existir, o nome no idioma do usuário será impresso. Se esse nome não existir, o nome do item será impresso.

- **Classificação tarifária do Sistema Harmonizado (HS)**: imprime a Cronograma de Tarifas Harmonizadas associada ao produto. Você pode configurar esses horários acessando **Gerenciamento de transporte \> Configuração \> Padrão de transporte \> Cronogramas de Tarifas Harmonizadas**.

- **Critério de origem:** você deve inserir dados manualmente nesta seção na primeira vez que liberar o documento.

- **País de origem:** imprime o país de origem, que você aplica acessando **Gerenciamento de informações sobre produtos \> Configuração \> Conformidade de produtos \> País de origem** (consulte também [País de origem](../pim/country-of-origin.md)). O código ISO para o país de origem é impresso com base no país/região de destino no endereço de entrega da remessa e no item. Se nenhum dado do país de origem foi configurado, então esse valor volta para a configuração encontrada em **Produto liberado \> Comércio exterior \> Origem**. Se ainda nenhum dado do país de origem for encontrado, você deve inserir manualmente o país de origem após gerar o documento.

### <a name="certifier-signature-and-date"></a>Assinatura e data do certificador

Você deve inserir isso manualmente após gerar o documento.

### <a name="consists-of-number-of-pages"></a>Consiste em número de páginas

O usuário que assina a certificação deve inserir manualmente o número de páginas (para verificação) após gerar o documento.

### <a name="page-numbers"></a>Números de página

Página atual e número de páginas impressas na parte inferior do documento.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]