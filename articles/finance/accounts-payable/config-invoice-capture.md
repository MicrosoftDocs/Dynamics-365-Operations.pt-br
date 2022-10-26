---
title: Configurar a solução Invoice Capture
description: Este artigo explica como configurar a solução Invoice Capture.
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
ms.openlocfilehash: e297dafc930368f14f2e68213ce4153ba792ef4d
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691123"
---
# <a name="configure-the-invoice-capture-solution"></a>Configurar a solução Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Depois que a solução Invoice Capture for instalada, você deve configurar o ambiente. O processo consiste nas seguintes etapas básicas.

1. **Obrigatório:** sincroniza as entidades legais do Microsoft Dynamics 365 Finance. Esta etapa é usada para configurar a estrutura da organização no Microsoft Power Platform.
2. **Obrigatório:** configura os canais para a importação de imagens de faturas. A solução suporta os seguintes canais:

    - Office 365 Outlook (padrão)
    - Outlook.com
    - OneDrive
    - SharePoint

3. **Opcional:** define grupos de configuração adicionais para o serviço de reconhecimento óptico de caracteres (OCR).
4. **Opcional:** define regras de mapeamento para a entidade legal, a conta do fornecedor, o item e o tipo de compras.

Este artigo se concentra nas duas etapas necessárias do processo. Para obter mais informações sobre grupos de configuração, consulte [Grupos de configuração da solução Invoice Capture](invoice-capture-config-group.md). Para obter mais informações sobre regras de mapeamento, consulte [Regras de mapeamento da solução Invoice Capture](invoice-capture-mapping-rules.md).

## <a name="manage-legal-entities"></a>Gerenciar entidades legais

O Finance define entidades legais como organizações que são identificadas por meio de registro junto às autoridades legais. As atividades comerciais são executadas e registradas em entidades legais separadas. No Microsoft Power Platform, as unidades de negócios, as funções de segurança e os usuários são vinculados de uma forma que está em conformidade com o modelo de segurança baseado na função.

As unidades de negócios são usadas juntamente com as funções de segurança para controlar o acesso aos dados. Os usuários veem somente as informações necessárias para realizar seus trabalhos. A solução Invoice Capture fornece um espaço de configuração no qual é possível carregar informações básicas de entidades legais existentes no Finance e gerenciar essas entidades criadas manualmente. As entidades legais são usadas em faturas do fornecedor e no controle de segurança.

Quando uma entidade legal é criada e mostrada no modo de exibição de lista, uma unidade de negócios padrão com o mesmo nome é criada automaticamente. A equipe recebe a função de segurança **Auxiliar do AP**. Quando as entidades legais são importadas, os dados mestre básicos do Finance são importados. Os itens inexistentes serão identificados pela entidade legal e serão adicionados à solução Invoice Capture. O grupo de configurações padrão é atribuído a novas entidades legais.

### <a name="sync-legal-entities"></a>Sincronizar entidades legais

Você não pode criar entidades legais diretamente. No entanto, você pode sincronizar entidades legais do Finance. Para sincronizar entidades legais, siga estas etapas.

1. Vá para **Configuração \> Configuração do sistema \> Gerenciar entidades legais**.
2. Selecione **Sincronizar entidades legal**, depois selecione **OK** na caixa de diálogo de confirmação.

Depois que a sincronização é concluída, o número de novas entidades legais é mostrado. As novas entidades legais são mostradas no modo de exibição de lista. O grupo de configurações padrão é atribuído a novas entidades legais.

## <a name="configure-invoice-import-channels"></a>Configurar canais de importação de fatura

Os fornecedores enviam faturas de diferentes canais (email, espaço de trabalho de arquivo ou portal de fatura) por meio de diferentes formatos (papel ou imagem). A solução Invoice Capture pode tratar de diferentes canais e formatos. Os seguintes tipos são suportados:

- Office 365 Outlook
- Outlook.com
- SharePoint
- OneDrive

Quando um canal é criado para uma conta específica, um fluxo automatizado que tem um modelo predefinido é criado para monitorar os emails ou os arquivos recebidos na caixa de entrada ou no espaço. Qualquer arquivo com uma fatura válida pode ser reconhecido e enviado para a área da fatura para aguardar o processamento pelo auxiliar de Contas a Pagar (AP). O anexo deve estar no formato PDF ou de imagem. As faturas podem ser carregadas na solução Invoice capture, de acordo com a configuração do canal.

### <a name="create-a-channel"></a>Criar um canal

Se você tiver importado o pacote de solução adicional (Dynamics 365 Invoice Capture – Ferramentas de Instalação), a conexão padrão do Office 365 Outlook estará pronta para ser usada. Se quiser criar mais conexões para diferentes contas de email ou outros tipos de canal, consulte [Criar conexões adicionais para canais](invoice-capture-advanced-settings.md#create-additional-connections-for-channels).

Para criar um canal, siga estas etapas.

1. Vá para **Configuração \> Configuração do sistema \> Canais de configuração**.
2. Selecione **Novo**.
3. Defina os seguintes campos:

    - Nome do canal
    - Descrição
    - Tipo
    - Conexão

Somente emails ou arquivos que correspondam aos critérios a seguir podem ser importados para a solução.

| Tipo               | Configuração  | Mais informações |
|--------------------|----------------|------------------|
| Office 365 Outlook | Pasta         | A pasta de email deve estar sob o diretório raiz. Por padrão, a pasta Caixa de Entrada é usada. Não há suporte para uma subpasta. |
|                    | Filtro de assunto | (Opcional) Uma substring que deve ser incluída no assunto. |
|                    | De           | (Opcional) O endereço de email do remetente ou dos remetentes. Se você especificar vários endereços, use um ponto-e-vírgula (;) como o separador. |
| SharePoint         | Endereço do Site   | O URL do endereço do site. |
|                    | Pasta         | A pasta no endereço do site. |

### <a name="activate-the-channel"></a>Ative o canal

Quando um fluxo é salvo, os campos mostram o status do canal e a hora em que ele foi criado. Inicialmente, o campo **Status** é definido como **Inativo**. O campo **Motivo do status** indica que o canal foi inicializado e está pronto para ser ativado.

Para ativar o canal, selecione **Ativar**. Os campos **Status** e **Motivo do status** são atualizados.

Se um canal não for necessário, você poderá desativá-lo. Para desativar um canal, selecione **Desativar**. Os campos **Status** e **Motivo do status** são atualizados.

### <a name="manage-flows-in-flow-management"></a>Gerenciar fluxos no gerenciamento de fluxo

Você pode exibir um canal na página **Canais de configuração** ou no gerenciamento de fluxo.

Para exibir mais detalhes, vá para **Sistema administrativo \> Solução padrão \> Fluxos da nuvem** e selecione o fluxo de destino. Os detalhes mostrados incluem conexões vinculadas, proprietários e históricos de execução.

Para sincronizar o status, selecione **Verificar** para confirmar que o status do canal corresponde ao status do fluxo.

Alguns casos de manipulação de exceção são mostrados no campo **Motivo do status**:

- **Conexão Dataverse ausente** – o usuário atual não criou pelo menos uma referência de conexão do **Microsoft Dataverse**.
- **Não encontrado** – o fluxo vinculado ao canal foi excluído no gerenciamento de fluxo. O canal deve ser salvo novamente para criar um novo canal.
- **Desativado no gerenciamento de fluxo** – o fluxo foi desativado no gerenciamento de fluxo e o status do canal é diferente do status do fluxo.
- **Ativado no gerenciamento de fluxo** – o fluxo foi ativado no gerenciamento de fluxo e o status do canal é diferente do status do fluxo.
- **Ocorreu um erro inesperado** – o usuário deve confirmar que o site é um "Site de comunicação" e que a pasta é "Biblioteca de documentos".
