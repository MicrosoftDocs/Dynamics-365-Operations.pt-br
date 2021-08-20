---
title: Trabalhar com a funcionalidade Mensagens eletrônicas
description: Este tópico fornece informações sobre como trabalhar com a funcionalidade Mensagens eletrônicas (EM).
author: liza-golub
ms.date: 07/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 8fd2301808f7eaec2ea9c01a66f030f527f461a36b3cb8aabddcfbf414f06d2a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6779899"
---
# <a name="work-with-the-electronic-messages-functionality"></a>Trabalhar com a funcionalidade Mensagens eletrônicas

[!include [banner](../includes/banner.md)]

Se você estiver trabalhando no nível da mensagem, a página **Mensagens eletrônicas** (**Imposto** \> **Consultas e relatórios** \> **Mensagens eletrônicas** \> **Mensagens eletrônicas**) é mais útil. Se você estiver trabalhando no nível da coleta de dados ou de item de mensagem, a página **Itens de mensagem eletrônica** (**Imposto** \> **Consultas e relatórios** \> **Mensagens eletrônicas** \> **Itens de mensagem eletrônica**) é mais útil.

## <a name="electronic-messages"></a>Mensagens eletrônicas

A página **Mensagens eletrônicas** apresenta o processamento que está disponível para você, com base em sua função. As funções de segurança estão associadas ao processamento na configuração desse processamento. Para cada processamento disponível para você, a página mostra mensagens eletrônicas e informações relacionadas a ele.

A FastTab **Mensagens** mostra mensagens eletrônicas para o processamento selecionado. Dependendo do status da mensagem selecionada e do processamento predefinido, você pode executar algumas ações usando os botões acima da grade:

- **Novo** – esse botão está associado a ações do tipo **Criar mensagem**.
- **Excluir** – Esse botão estará disponível se a caixa de seleção **Permitir exclusão** estiver marcada para o status atual da mensagem selecionada.
- **Coletar dados** — esse botão está associado com ações do tipo **Preencher registros**.
- **Gerar relatório** – esse botão está associado a ações do tipo **Mensagem de exportação de relatórios eletrônicos**.
- **Enviar relatório** – esse botão está associado a ações do tipo **Serviço Web**.
- **Importar a resposta** — esse botão está associado com ações do tipo **Importação de relatório eletrônico**.
- **Status da atualização** – esse botão está associado a ações do tipo **Processamento de usuário no nível da mensagem**.
- **Itens de mensagem** – abra a página **Itens de mensagem eletrônica**.

A FastTab **Log de ação** mostra informações sobre todas as ações executadas para a mensagem selecionada. Se uma ação causar em um erro, as informações sobre o erro serão anexadas à linha relacionada na grade. Para examinar as informações sobre o erro, selecione a linha na grade, selecione o botão **Anexo** (o símbolo de clipe de papel) no canto direito superior na página.

A FastTab **Campos adicionais da mensagem** mostra todos os campos adicionais definidos para mensagens na configuração de processamento. A guia rápida também inclui os valores desses campos adicionais.

A FastTab **Itens de mensagem** mostra todos os itens de mensagem relacionados à mensagem selecionada. Dependendo do status do item de mensagem selecionado, você pode executar algumas ações usando os botões acima da grade:

- **Excluir** – Este botão estará disponível se a caixa de seleção **Permitir exclusão** estiver marcada para o status atual do item de mensagem selecionado.
- **Status da atualização** – Este botão está associado a ações do tipo **Processamento do usuário**.
- **Documento original** — abre uma página que exibe o documento original para o item de mensagem selecionado.

Os relatórios que já foram já gerados e recebidos de uma mensagem são anexados à mensagem. Para examinar os anexos relacionados a uma mensagem, selecione a mensagem, selecione o botão **Anexo** (o símbolo de clipe de papel) no canto direito superior da página.

![Botão Anexo](media/attachment-icon.png)

A página **Anexos** mostra os anexos relacionados à mensagem selecionada. Para exibir um arquivo, selecione-o na lista à esquerda e depois selecione **Abrir** no Painel de Ações.

![Botão Abrir](media/open-button.png)

Você pode examinar os anexos relacionadas a uma ação específica que foi executada anteriormente para uma mensagem. Na página **Mensagens eletrônicas**, na guia rápida **Mensagens**, selecione a mensagem. Na guia rápido **Registro da ação**, selecione a ação depois selecione o botão **Anexo** (símbolo de clipe de papel) no canto superior direito da página.

Você pode executar todo o processamento ou apenas uma ação específica, selecionando **Executar processamento** no Painel de Ações.

## <a name="electronic-message-items"></a>Itens de mensagem eletrônica

A página **Itens de mensagem eletrônica** mostra todos os itens de mensagem e um log das ações executadas para cada item de mensagem. A página também mostra os campos adicionais definidos para os itens de mensagem, e os valores desses campos adicionais.

A tabela a seguir descreve os campos na guia **Itens de mensagem**.

<table>
<thead>
<tr>
<th>Campo</th>
<th>descrição</th>
</tr>
</thead>
<tbody>
<tr>
<td>Processando</td>
<td>O nome de processamento usado para criar o item de mensagem.</td>
</tr>
<tr>
<td>Item da mensagem</td>
<td>A ID do item de mensagem. Essa ID é atribuída automaticamente com base na sequência numérica do <b>Item de mensagem</b> definida na página <b>Parâmetros de contabilidade</b>.</td>
</tr>
<tr>
<td>Data do item de mensagem</td>
<td>A data em que o item de mensagem foi criado.</td>
</tr>
<tr>
<td>Tipo de item de mensagem</td>
<td>O tipo de item de mensagem. Vários tipos de itens de mensagem podem ser configurados para o mesmo processamento (por exemplo, <b>Faturas de entrada</b> e <b>Faturas de saída</b>). Esse campo só poderá ser definido automaticamente quando uma fatura for adicionada à tabela Itens de mensagem.</td>
</tr>
<tr>
<td>Status de item de mensagem</td>
<td><p>O status real do item de mensagem. Os status disponíveis variam, dependendo do tipo de item de mensagem. Eis alguns exemplos:</p>
<ul>
<li><b>Preenchido</b> – um registro foi adicionado à tabela Itens de mensagem.</li>
<li><b>Avaliado</b> – atributos adicionais foram calculados para o item de mensagem.</li>
<li><b>Relatado</b> – o item de mensagem foi adicionado com êxito a um relatório.</li>
<li><b>Excluído</b> – O status é útil se você tiver de excluir alguns itens de mensagem de um relatório antes de exportar.</li>
</ul>
</td>
</tr>
<tr>
<td>Data de transmissão</td>
<td>Para o processamento que transmite automaticamente um relatório gerado fora do sistema, a data em que o item de mensagem foi transmitido.</td>
</tr>
<tr>
<td>Número do documento</td>
<td>Esse campo é definido automaticamente, com base na configuração da ação de preencher registros. Esse campo só poderá ser definido automaticamente quando uma fatura for adicionada à tabela Itens de mensagem.</td>
</tr>
<tr>
<td>Número da conta</td>
<td>O número da conta de um cliente ou fornecedor (ou outro valor de campo, dependendo do campo definido na ação de preencher registros). Esse campo só poderá ser definido automaticamente quando uma fatura for adicionada à tabela Itens de mensagem.</td>
</tr>
<tr>
<td>Mensagem</td>
<td>O número da mensagem. Esse número é atribuído automaticamente, com base na sequência numérica do <b>Item de mensagem</b> definida na página <b>Parâmetros de contabilidade</b>.</td>
</tr>
<tr>
<td>Status da mensagem</td>
<td>O status real da mensagem eletrônica.</td>
</tr>
<tr>
<td>Próxima ação</td>
<td>As próxima ações que podem ser iniciadas para o status atual do item da mensagem.</td>
</tr>
</tbody>
</table>

A guia **Campos adicionais** mostra os campos adicionais para o item de mensagem selecionado e seus valores.

### <a name="run-processing"></a>Executar processamento

No Painel de Ações, selecione **Executar processamento** para executar o processamento para itens de mensagem. Para executar uma ação específica, na caixa de diálogo **Executar processamento** , defina a opção **Escolher ação** como **Sim**, e selecione uma ação. Para executar o processamento inteiro, deixe a opção **Escolher ação** definida como **Não**.

### <a name="generate-report"></a>Gerar relatório

No Painel de Ações, selecione **Gerar relatório**. Esse botão está associado a ações do tipo **Exportação de relatórios eletrônicos**.

### <a name="update-status"></a>Atualizar Status

No Painel de Ações, selecione **Atualizar status** para atualizar o status de um ou mais itens de mensagem. Na caixa de diálogo **Atualizar status**, use a FastTab **Registros a serem incluídos** para selecionar os itens de mensagem a serem atualizados. Cerifique-se de definir corretamente os critérios de seleção, porque os status de itens de mensagem serão atualizados de acordo com esses critérios, o status inicial da ação selecionada e o valor que você especificar no campo **Novo status**. Depois que uma atualização de status for concluída, será difícil determinar quais itens foram atualizados. Portanto, será difícil reverter a atualização de status.

### <a name="electronic-messages"></a>Mensagens eletrônicas

No Painel de Ações, selecione **Mensagens eletrônicas** para examinar uma mensagem eletrônica que esteja relacionada ao item de mensagem selecionado.

Você também pode examinar os arquivos relacionados a um item de mensagem específico. Selecione o campo **Mensagem** no item da mensagem ou, no Painel de Ações, selecione **Mensagens eletrônicas**. Na página **Mensagem eletrônica**, selecione a mensagem para examinar os arquivos e selecione o botão **Anexo** (símbolo de clipe de papel) no canto superior direito da página.

A página **Anexos** mostra os anexos relacionados à mensagem. Para exibir um arquivo, selecione-o na lista à esquerda e então selecione **Abrir** no Painel de Ações.

### <a name="original-document"></a>Documento original

No Painel de Ações, selecione **Documento original** para abrir o documento original para o item de mensagem selecionado.
