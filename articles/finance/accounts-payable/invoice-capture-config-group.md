---
title: Grupos de configuração da solução Invoice Capture
description: Este artigo fornece informações gerais sobre grupos de configurações na solução Invoice Capture.
author: sunfzam
ms.date: 09/28/2022
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
ms.openlocfilehash: cfe5ae35b4f87a350d944b30a49251081766ad27
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691127"
---
# <a name="invoice-capture-solution-configuration-groups"></a>Grupos de configuração da solução Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Os usuários podem gerenciar a lista de campos da fatura e a configuração de revisão manual para entidades legais usando grupos de configuração. Os usuários podem definir configurações de fatura para diferentes entidades legais em grupos. Todas as entidades legais no mesmo grupo de configuração usam os mesmos campos de fatura e configuração de revisão manual.

## <a name="manage-configuration-groups"></a>Gerenciar grupos de configuração

Para gerenciar grupos de configuração usando o aplicativo, vá para **Configuração** e selecione **Configuração do sistema \> Definir componente dos grupos de configuração**.

Na página **Definir grupos de configuração**, a principal guia mostra a lista de grupos de configuração que foram definidas. Também mostra um grupo de configuração padrão. Para cada grupo de configuração, as seguintes ações estão disponíveis:

- **Copiar um grupo de configuração** – Você pode criar um novo grupo de configuração duplicando um grupo existente. O novo grupo tem os mesmos valores que o grupo original para todos os campos, exceto **Nome do grupo** e **Descrição do grupo**. Depois que o grupo de configurações for duplicado, selecione **OK**.
- **Excluir grupos de configuração** – para excluir um grupo de configurações, selecione-o e, em seguida, selecione **Excluir**.

    > [!NOTE]
    > O grupo de configurações padrão não pode ser excluído.

- **Editar a ID de um grupo de configurações** – Para editar a ID de um grupo de configurações, selecione o campo **ID do Grupo** e atualize o valor. A ID do grupo não deve conter espaços, nem caracteres especiais e não deve exceder 20 caracteres.

    > [!NOTE]
    > O valor do campo **ID do Grupo** pode ser atualizado somente uma vez.

- **Editar uma descrição de um grupo de configurações** – Para editar a descrição de um grupo de configurações, selecione o campo **Descrição** e atualize o valor.
- **Alterar a configuração de revisão manual** – Os usuários podem decidir se uma fatura deve ser revisada manualmente. Para alterar a configuração de revisão manual, selecione a opção **Precisa de revisão manual**. As opções a seguir estão disponíveis:

    - **Revisão manual sempre** – Selecione esta opção se as faturas no grupo de configurações sempre exigirem revisão manual.
    - **Para erros e avisos** – Selecione esta opção se as faturas que contêm mensagens de erro ou mensagens de aviso exigirem revisão manual.
    - **Para erros** – Selecione esta opção se as faturas que contêm mensagens de erro exigirem revisão manual.

- **Alterar a configuração de pontuação de confiança** – a pontuação de confiança é metadados que a solução Invoice capture fornece para relatar a precisão dos dados da fatura reconhecidos. Quanto mais alta for a pontuação, mais precisos serão os dados reconhecidos. A configuração permite que os usuários definam quando a revisão manual é necessária, com base na pontuação de confiança. Os usuários podem alterar o limite de pontuação de confiança para faturas. Para atualizar a configuração de pontuação de confiança, selecione o campo **Pontuação de confiança** e atualize o valor.

    Há dois tipos de alerta para pontuações de confiança:

    - **Aviso** – os campos da fatura com pontuações de confiança acima do limite de aviso são considerados corretos. O limite de aviso deve ser maior do que o limite de erro e menor que 100.
    - **Erro** – os campos da fatura com pontuações de confiança abaixo do limite de erro são considerados com falha. As mensagens de erro serão mostradas ao usuário. O limite de erro deve ser maior do que 0 (zero) e menor que o limite de aviso. Mensagens de aviso serão mostradas para os campos da fatura que têm uma pontuação de confiança entre o limite de aviso e o limite de erro.

- **Gerenciar campos da fatura** – os usuários podem gerenciar a lista de campos da fatura mostrados no visualizador lado a lado. Na guia **Gerenciamento de campo da fatura**, selecione o símbolo de engrenagem, selecione os campos de fatura a serem adicionados e, em seguida, selecione **Salvar**. Os campos selecionados serão adicionados à lista. Para remover um campo da fatura da lista, selecione **Remover** do campo.

### <a name="manage-file-filters-optional"></a>Gerenciar filtros do arquivo (opcional)

Gerenciar filtros de arquivos permite que os usuários definam filtros adicionais para os arquivos da fatura de entrada. Os arquivos que não atendem aos critérios de filtragem serão recebidos e aparecerão na lista **Arquivos recebidos**, mas eles mostrarão erros de validação de arquivos. Esse comportamento é diferente do comportamento de filtros definidos no canal. Para esses filtros, os arquivos que não atendem aos critérios não serão recebidos. Os usuários podem revisar os arquivos de entrada e decidir se cada arquivo é uma fatura não válida e se eles podem ficar obsoletos ou, manualmente, incluí-lo para reconhecimento e inclusão em faturas capturadas.

Quando a solução Invoice capture é instalada, um filtro de arquivo padrão é definido. Esse filtro de arquivo é global. Se quiser configurações de filtro diferentes, você poderá atualizar o filtro padrão. Se um campo for obrigatório, selecione **Obrigatório**. 

### <a name="accepted-file-size"></a>Tamanho de arquivo aceito

Você pode escolher o tamanho do arquivo aceito.

> [!NOTE]
> Não há suporte para arquivos maiores que 20.480 kilobytes (KB).

### <a name="supported-file-types"></a>Tipos de arquivo com suporte

Atualmente, há suporte para os seguintes tipos de arquivos:

- PDF
- PNG
- JPG
- JPEG
- TIF
- TIFF
