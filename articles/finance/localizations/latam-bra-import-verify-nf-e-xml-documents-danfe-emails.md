---
title: Importação e verificação de documentos XML da NF-e e os arquivos de DANFE para o Brasil
description: Este artigo fornece informações sobre como importar e verificar os documentos XML de Nota fiscal eletrônica (NF-e) e o Documento Auxiliar da Nota Fiscal Eletrônica (DANFE) que você recebeu.
author: sndray
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 269134
ms.assetid: d4c1d39b-64ec-4ddf-ba27-c0446f80f031
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5093a8994f1dbbab0ede486ff1f8d53d4240d974
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872359"
---
# <a name="import-and-verify-nf-e-xml-documents-and-danfe-files-for-brazil"></a>Importação e verificação de documentos XML da NF-e e os arquivos de DANFE para o Brasil

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre como importar e verificar os documentos XML de Nota fiscal eletrônica (NF-e) e o Documento Auxiliar da Nota Fiscal Eletrônica (DANFE) que você recebeu.

Você pode realizar as seguintes tarefas para configurar os documentos XML de Nota fiscal eletrônica (NF-e) e os arquivos do Documento Auxiliar da Nota Fiscal Eletrônica (DANFE) que você recebe por e-mail:

-   Configurar contas de e-mail para importar documentos XML e arquivos DANFE para notas fiscais eletrônicas.
-   Configure o código do Instituto Brasileiro de Geografia e Estatistica (IBGE) de um estado, e configure uma autoridade estatal.
-   Importe os documentos XML da NF-e e os arquivos de DANFE recebidos nos e-mails e, em seguida, execute as seguintes tarefas:
    -   Exibir o documento XML de uma NF-e.
    -   Exibir o DANFE para um documento XML de NF-e.
    -   Use a chave de acesso para verificar o status da NF-e na Secretaria da Fazenda (SEFAZ).
-   Insira manualmente uma chave de acesso para uma NF-e para a qual você não recebeu um documento XML.
-   Lance as notas fiscais eletrônicas que possuem as chaves de acesso que não foram validadas pela SEFAZ. Você também pode configurar o Dynamics 365 Finance para lançar somente as notas fiscais eletrônicas com as chaves de acesso validadas pela SEFAZ.
-   Se você lançar as notas fiscais eletrônicas e as chaves de acesso não estiverem disponíveis na página **Documentos XML de NF-e recebidos**, atualize as chaves de acesso ou os documentos XML após o lançamento. É possível exibir os documentos de NF-e lançados que exigem chaves de acesso ou documentos XML. Esses documentos incluem:
    -   Documentos de NF-e que possuem as chaves de acesso que não foram validadas pela SEFAZ.
    -   Documentos de NF-e para os quais o status é atualizado de **Aprovado** para **Cancelado**.
    -   Documentos de NF-e para os quais os anexos de XML não estão disponíveis.
    -   Documentos de NF-e para os quais as chaves de acesso não estão disponíveis nos documentos XML de NF-e recebidos.
-   Exibir as notas fiscais que não são lançadas, mas para as quais você recebeu a chave de acesso.

É possível configurar o Finance para verificar o status das chaves de acesso da NF-e na SEFAZ várias vezes. Neste caso, a última consulta é feita depois do período no qual o fornecedor deve cancelar uma NF-e aprovada.

## <a name="how-do-i-import-xml-documents-and-danfe-files-from-emails"></a>Como importar documentos XML e arquivos de DANFE de e-mails?
Você pode usar a página **Importar arquivos XML de email** para importar documentos XML e arquivos de DANFE para documentos de NF-e de email. Antes de importar os arquivos, é necessário configurar contas de e-mail que serão usadas para importar documentos XML e arquivos de DANFE para a NF-e.

## <a name="can-i-manually-update-the-access-key-for-an-nf-e-that-i-didnt-receive-the-xml-document-for"></a>Posso atualizar manualmente a chave de acesso manualmente para uma NF-e cujo documento XML ainda não recebi?
Sim, é possível atualizar a chave de acesso manualmente para uma NF-e cujo documento XML você não recebeu. Você pode gerar primeiro a lista de documentos de NF-e para os quais as chaves de acesso não estão disponíveis nos documentos XML de NF-e. Para gerar esta lista, na página **NF-e lançadas pendentes de validação**, selecione a opção **Chave de acesso não encontrada em XML de NF-e recebidos**. Em seguida na página **Documentos XML de NF-e recebidos**, atualize a chave de acesso no campo **NF-e na chave de acesso**.

## <a name="can-i-post-an-nf-e-document-without-validating-the-access-key"></a>Posso lançar um documento de NF-e sem validar a chave de acesso?
Sim, você pode. Você pode validar as chaves de acesso para esses documentos de NF-e após o lançamento ser concluído. Para gerar uma lista de documentos de NF-e com as chaves de acesso que não forem validadas pela SEFAZ, selecione **Status não consultado na SEFAZ** na página **NF-e lançada com validação pendente**. Para lançar somente as notas fiscais eletrônicas que tenham chaves de acesso validadas, selecione **Lançar somente NF-e com chaves de acesso válidas** na página **Estabelecimentos fiscais**.

## <a name="how-do-i-check-the-status-of-nf-e-access-keys-at-the-sefaz"></a>Como verifico o status das chaves de acesso de NF-e na SEFAZ?
Você pode usar a página **Consulta de XML recebido** para verificar o status das chaves de acesso da NF-e na SEFAZ. As consultas sobre o status das chaves de acesso serão efetuadas várias vezes antes da NF-e ser aprovada. Além disso, uma última consulta sobre o status é feita depois do período no qual o fornecedor deve cancelar uma NF-e aprovada.

## <a name="how-do-i-generate-a-list-of-nf-e-documents-that-werent-posted-but-that-i-received-the-xml-documents-for"></a>Como gero uma lista de documentos de NF-e que não foram lançados, mas para os quais recebi os documentos XML?
Na página **Documentos XML de NF-e recebidos**, selecione **Lançados** para verificar os documentos da NF-e para os quais você recebeu os documentos XML, mas que não foram lançados.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]