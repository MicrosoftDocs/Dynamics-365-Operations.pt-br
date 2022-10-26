---
title: Espaço de trabalho da solução do Invoice Capture
description: Este artigo fornece informações sobre o espaço de trabalho de solução do Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4f3af7abf94542437be6132344d6bb7ffaf33d07
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691124"
---
# <a name="invoice-capture-solution-workspace"></a>Espaço de trabalho da solução do Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="side-by-side-viewer-for-the-invoice-capture-solution"></a>Visualizador lado a lado da solução do Invoice Capture

A inserção de faturas no sistema costuma ser um processo demorado propenso a erros, pois os auxiliares devem navegar em vários arquivos de anexo e janelas para coletar as informações corretas. O visualizador de documentos lado a lado ajudará a melhorar a sua experiência ao trabalhar em faturas, tornando o processo mais fácil, eficiente e preciso.

O visualizador de documentos lado a lado permite que os usuários tenham o documento original e a fatura aberta lado a lado na mesma janela. A página de fatura é preenchida com informações obtidas do documento de fatura original. O visualizador cria a conexão entre os campos de página de fatura e o documento de fatura original. O visualizador também ajuda os usuários a localizar erros existentes na página de fatura.

### <a name="open-the-side-by-side-viewer"></a>Abra o visualizador lado a lado

No Microsoft Dynamics 365 Finance, você pode abrir o visualizador lado a lado da lista na página de resumo ou na página de lista de faturas. Você também pode abri-lo ao tocar duas vezes (ou clicar duas vezes) em um registro ou ao selecionar o número da fatura.

### <a name="using-the-side-by-side-viewer"></a>Usar o visualizador lado a lado

#### <a name="manually-review-an-invoice"></a>Revisar manualmente uma fatura

Um documento de fatura importado pode exigir revisão manual devido a erros ou avisos. No visualizador lado a lado, o cabeçalho do documento mostrará um status **Importado** e a versão atual será **Versão Original**.

Para começar a revisar a fatura, selecione **Iniciar revisão**. Todos os campos se tornam editáveis. O campo **Status** é atualizado para **Em revisão** e o campo **Versão atual** é atualizado para **Versão modificada**.

#### <a name="view-and-work-with-messages"></a>Exibir e trabalhar com mensagens

Os usuários devem iniciar o processo de revisão no painel de mensagens. As mensagens de erro são indicadas por um X vermelho, as mensagens de aviso são indicadas por um triângulo e as mensagens informativas são indicadas por um círculo. É possível classificar mensagens relativas à pontuação de confiança como avisos ou erros, dependendo do limite definido pelo grupo de configurações. Para obter mais informações, consulte [Grupos de configuração da solução Invoice Capture](invoice-capture-config-group.md).

É possível ignorar mensagens de aviso e de erro no painel de mensagens, no cabeçalho da fatura ou em linhas da fatura. Depois que uma mensagem é ignorada, ela não aparece mais como um erro ou aviso e a fatura não falha na validação.

- Para ignorar mensagens do painel de mensagens, selecione **Ignorar**. Para redefinir uma mensagem que foi ignorada, selecione **Ignorar** novamente. O tipo é alterado de erro ou aviso para informações.
- Para ignorar mensagens do cabeçalho da fatura ou da linha da fatura, selecione **Ignorar** no campo. O símbolo da mensagem desaparece. No entanto, ele reaparecerá se a mensagem for redefinida no painel de mensagens.

Para mensagens relacionadas a campos de cabeçalho de fatura, quando você seleciona a mensagem no painel de mensagens, o cursor é movido para o campo correspondente na seção de cabeçalho.

#### <a name="proofread-and-edit-fields"></a>Revisar e editar campos

Se o valor de um campo for lido da fatura original por meio do OCR (reconhecimento óptico de caracteres), um símbolo aparecerá no campo. Se você selecionar o símbolo, o visualizador de documentos ampliará e realçará o local em que o valor do campo é lido, para ajudá-lo a verificar os dados da fatura.

Para redefinir o visualizador de documentos para a ampliação original, siga uma destas etapas:

- Selecione o mesmo símbolo selecionado anteriormente.
- Selecione o botão no canto superior direito do visualizador de documentos.

Edite os campos, conforme necessário. As edições são salvas automaticamente quando o cursor sai de um campo. Um símbolo à direita de um campo indica que o campo foi atualizado manualmente. Quando a página for atualizada, o símbolo será removido.

#### <a name="check-an-invoice-to-get-up-to-date-messages"></a>Verificar uma fatura para obter mensagens atualizadas

Quando você edita um campo, o valor do campo é atualizado, mas novas mensagens de validação não são geradas. Para obter mensagens de validação atualizadas, selecione **Verificar**. As mensagens no painel de mensagens, no cabeçalho da fatura e nas linhas da fatura são atualizadas.

#### <a name="complete-the-review"></a>Concluir a revisão

Para concluir a revisão, selecione **Concluir revisão**. As faturas são validadas. Se forem encontrados erros, o status do documento permanecerá **Em revisão** e uma barra de mensagens aparecerá. Todas as mensagens no painel de mensagens e no cabeçalho e linhas da fatura são atualizadas automaticamente para fornecer informações sobre as causas da falha na validação.

Após a correção de todos os erros de bloqueio, a revisão pode ser concluída. O status do documento é atualizado para **Revisado** e não é mais possível editar os campos. Para reiniciar a revisão, selecione **Iniciar revisão** novamente.

#### <a name="generate-a-pending-vendor-invoice-in-finance"></a>Gerar uma fatura pendente do fornecedor no Finance

Para enviar o documento de fatura para o ambiente conectado do Finance, selecione **Gerar**. Se a geração da fatura falhar, uma mensagem de erro aparecerá em uma barra de mensagens.

#### <a name="void-an-invoice"></a>Anular uma fatura

Para anular uma fatura, selecione **Anular**. As faturas anuladas não podem ser revisadas e não são mostradas na lista **As faturas precisam de revisão manual**.

### <a name="validation-logic"></a>Lógica de validação

Alguns campos-chave do visualizador lado a lado não existem nos dados de preparo da fatura, mas são necessários para gerar faturas pendentes no Finance. Esses campos derivam de uma combinação dos dados de preparo da fatura atual e dos dados mestre do Finance.

Os campos que devem ser derivados são **Entidade Legal**, **Conta de Fornecedor** e **Número de Item**. Eles devem ser derivados na ordem a seguir. Se a derivação de um campo falhar, o processo será interrompido.

1. **Entidade legal** – a entidade legal é derivada primeiro. Se uma regra de mapeamento ativo for encontrada para a entidade legal, essa entidade será derivada com base no nome e no endereço da empresa.
2. **Conta de fornecedor** – em seguida, a conta do fornecedor é derivada com base em uma regra de mapeamento ativa e uma combinação da entidade legal derivada e do nome do fornecedor e do endereço do fornecedor.
3. **Número do item** – finalmente, o nome do item é derivado de preparo, com base nos seguintes três tipos de informações:

    - Uma regra de mapeamento configurado
    - A entidade legal derivada
    - A conta do fornecedor derivada

Para executar uma validação, selecione **Verificar** no visualizador lado a lado. No momento, a validação executa as seguintes verificações:

- **Verificação obrigatória** – essa verificação valida os campos obrigatórios do visualizador lado a lado. Os usuários podem selecionar quais campos devem ser obrigatórios na página **Definição de configuração**.
- **Pontuação de confiança** – os usuários podem definir o limite de aviso e o limite de erro para a pontuação de confiança. Essa verificação se concentra na pontuação de confiança do OCR que está abaixo desses limites. Mensagens de erro ou de aviso serão mostradas com base no resultado da validação.
- **Entidade legal** – essa verificação valida que uma entidade legal está em Finance. Se a entidade legal não existir no ambiente do Finance, a validação falhará.

Quando o visualizador lado a lado é usado pela primeira vez e o usuário seleciona **Verificar**, os processos de derivação e validação são executados. Se as faturas forem precisas, o processo de validação será executado quando o usuário selecionar **Concluir revisão**. Ele também é executado quando o usuário seleciona **Gerar fatura de fornecedor**.

O processo de derivação ocorre antes do processo de validação e todos os avisos ou erros derivam do processo de validação. Os avisos e os erros serão registrados no Finance.
