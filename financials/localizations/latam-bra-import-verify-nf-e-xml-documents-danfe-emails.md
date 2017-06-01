---
title: "Importação e verificação de documentos XML da NF-e e os arquivos de DANFE para o Brasil"
description: "Este tópico responde questões sobre o processo de importar e verificar os documentos XML da Nota fiscal eletrônica (NF-e) e o Documento Auxiliar da Nota Fiscal Eletrônica (DANFE) que você recebe por e-mail."
author: sndray
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations, Core
ms.custom: 269134
ms.assetid: d4c1d39b-64ec-4ddf-ba27-c0446f80f031
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: c10a0692437302e187d01c3c0e5779f35eb58eb4
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="import-and-verify-nf-e-xml-documents-and-danfe-files-for-brazil"></a>Importação e verificação de documentos XML da NF-e e os arquivos de DANFE para o Brasil

[!include[banner](../includes/banner.md)]


Este tópico responde questões sobre o processo de importar e verificar os documentos XML da Nota fiscal eletrônica (NF-e) e o Documento Auxiliar da Nota Fiscal Eletrônica (DANFE) que você recebe por e-mail.

Você pode realizar as seguintes tarefas para configurar os documentos XML de Nota fiscal eletrônica (NF-e) e os arquivos do Documento Auxiliar da Nota Fiscal Eletrônica (DANFE) que você recebe por e-mail:

-   Configurar contas de e-mail para importar documentos XML e arquivos DANFE para notas fiscais eletrônicas.
-   Configure o código do Instituto Brasileiro de Geografia e Estatistica (IBGE) de um estado, e configure uma autoridade estatal.
-   Importe os documentos XML da NF-e e os arquivos de DANFE recebidos nos e-mails e, em seguida, execute as seguintes tarefas:
    -   Exibir o documento XML de uma NF-e.
    -   Exibir o DANFE para um documento XML de NF-e.
    -   Use a chave de acesso para pesquisar o status atual da NF-e na Secretaria da Fazenda (SEFAZ).
-   Insira manualmente uma chave de acesso para uma NF-e para a qual você não recebeu um documento XML.
-   Lance as notas fiscais eletrônicas que possuem as chaves de acesso que não foram validadas pela SEFAZ. Como alternativa, você pode configurar o Microsoft Dynamics 365 for Operations para lançar somente as notas fiscais eletrônicas com as chaves de acesso validadas pela SEFAZ.
-   Se você lançar as notas fiscais eletrônicas para as quais as chaves de acesso não estão disponíveis na página **Documentos XML de NF-e recebidos**, será possível atualizar as chaves de acesso ou documentos XML para as notas fiscais eletrônicas após a conclusão do lançamento. É possível exibir os seguintes documentos de NF-e lançados que requerem chaves de acesso ou documentos XML:
    -   Documentos de NF-e que possuem as chaves de acesso que não foram validadas pela SEFAZ.
    -   Documentos de NF-e para os quais o status é atualizado de **Aprovado** para **Cancelado**.
    -   Documentos de NF-e para os quais os anexos de XML não estão disponíveis.
    -   Documentos de NF-e para os quais as chaves de acesso não estão disponíveis nos documentos XML de NF-e recebidos.
-   Exibir as notas fiscais que não são lançadas, mas para as quais você recebeu a chave de acesso.

Também é possível configurar o Dynamics 365 for Operations para consultar várias vezes o status das chaves de acesso da NF-e na SEFAZ. Neste caso, a última consulta é feita depois do período no qual o fornecedor deve cancelar uma NF-e aprovada.

## <a name="how-do-i-import-xml-documents-and-danfe-files-from-emails"></a>Como importar documentos XML e arquivos de DANFE de e-mails?
Você pode usar a página **Importar arquivos XML de email** para importar documentos XML e arquivos de DANFE para documentos de NF-e de email. Antes de importar os arquivos, é necessário configurar contas de e-mail que serão usadas para importar documentos XML e arquivos de DANFE para a NF-e.

## <a name="can-i-manually-update-the-access-key-for-an-nfe-that-i-didnt-receive-the-xml-document-for"></a>Posso atualizar manualmente a chave de acesso manualmente para uma NF-e cujo documento XML ainda não recebi?
Sim, é possível atualizar a chave de acesso manualmente para uma NF-e cujo documento XML você não recebeu. Você pode gerar primeiro a lista de documentos de NF-e para os quais as chaves de acesso não estão disponíveis nos documentos XML de NF-e. Para gerar esta lista, na página **NF-e lançadas pendentes de validação**, selecione a opção **Chave de acesso não encontrada em XML de NF-e recebidos**. Em seguida na página **Documentos XML de NF-e recebidos**, atualize a chave de acesso no campo **NF-e na chave de acesso**.

## <a name="can-i-post-an-nfe-document-without-validating-the-access-key"></a>Posso lançar um documento de NF-e sem validar a chave de acesso?
Sim, você pode lançar um documento de NF-e sem validar a chave de acesso. Você pode validar as chaves de acesso para esses documentos de NF-e após o lançamento ser concluído. Para gerar uma lista de documentos de NF-e com as chaves de acesso que não forem validadas pela SEFAZ, na página **NF-e lançada com validação pendente**, selecione a opção **Status não consultado na SEFAZ**. Alternativamente, para lançar somente os documentos eletrônicos fiscais que têm as chaves de acesso validadas pela SEFAZ, na página **Estabelecimentos fiscais**, na Guia Rápida **NF-e federal**, selecione a opção **Lançar somente NF-e com chave de acesso validada**.

## <a name="how-do-i-inquire-about-the-status-of-nfe-access-keys-at-the-sefaz"></a>Como pesquiso o status das chaves de acesso de NF-e na SEFAZ?
Você pode usar a página **Consulta de XML recebido** para consultar o status das chaves de acesso da NF-e na SEFAZ. As consultas sobre o status das chaves de acesso serão efetuadas várias vezes antes da NF-e ser aprovada. Além disso, uma última consulta sobre o status é feita depois do período no qual o fornecedor deve cancelar uma NF-e aprovada.

## <a name="how-do-i-generate-a-list-of-nfe-documents-that-werent-posted-but-that-i-received-the-xml-documents-for"></a>Como gero uma lista de documentos de NF-e que não foram lançados, mas para os quais recebi os documentos XML?
É possível usar a opção **Lançados** na página **Documentos XML de NF-e recebidos** para verificar os documentos da NF-e que não foram lançados, mas para os quais você recebeu os documentos XML.




