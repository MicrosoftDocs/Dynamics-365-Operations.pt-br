---
title: Importar e verifique documentos XML de NF-e e arquivos de DANFE para O Brasil
description: "Esse tópico atende perguntas sobre o processo de importação e fiscal eletrônica auxiliar fiscal verificando de documentos XML Do Documento e à Nota fiscal eletrônica de NF-e) Nota ((DANFE) que você recebe de email."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269134
ms.assetid: d4c1d39b-64ec-4ddf-ba27-c0446f80f031
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 47618e885d16092ec43ec01186224e6ee4c243f8
ms.lasthandoff: 03/31/2017


---

# <a name="import-and-verify-nf-e-xml-documents-and-danfe-files-for-brazil"></a>Importar e verifique documentos XML de NF-e e arquivos de DANFE para O Brasil

Esse tópico atende perguntas sobre o processo de importação e fiscal eletrônica auxiliar fiscal verificando de documentos XML Do Documento e à Nota fiscal eletrônica de NF-e) Nota ((DANFE) que você recebe de email.

Você pode executar as seguintes tarefas de importar fiscal eletrônica de documentos XML Do Documento e à Nota fiscal eletrônica de Nota fiscal os arquivos auxiliares NF-e () (DANFE) que você recebe de email:

-   Contas de email de instalação para importar documentos XML e arquivos de DANFE para notas fiscais eletrônicos.
-   Configure o código do Instituto Brasileiro de Geografia e Estatistica (IBGE) de um estado, e configure uma autoridade estatal.
-   Importar documentos XML de NF-e e arquivos de DANFE recebidos em email, e execute as seguintes tarefas:
    -   Exibir o documento XML de uma NF-e.
    -   Exibir o DANFE para um documento XML de NF-e.
    -   Use uma tecla de acesso para consultar o status atual de NF-e Secretaria da Fazenda (Dinamarca). A SEFAZ
-   Insira manualmente uma tecla de acesso para um NF-e quais você não recebeu para um documento XML.
-   Lançar as notas fiscais eletrônicos com as teclas de acesso que não são. por validadas SEFAZ Alternativamente, você pode configurar o Microsoft Dynamics 365 para as operações lancem somente os documentos eletrônicos fiscais que têm as teclas de acesso validadas. por SEFAZ
-   Caso lance as notas fiscais eletrônicos das teclas de acesso não disponíveis ** documentos XML recebidos de NF-e ** na página, pode atualizar as teclas de acesso ou documentos XML para as notas fiscais eletrônicos após o lançamento ser concluído. Você pode exibir os seguintes documentos lançados de NF-e que necessitem tecla de acesso ou documentos XML:
    -   Documentos de NF-e com as teclas de acesso que não são. por validadas SEFAZ
    -   Para documentos de NF-e de que o status é atualizado ** aprovado ** a ** ** cancelado.
    -   Documentos de NF-e os anexos XML não estão disponíveis para.
    -   Documentos de NF-e das teclas de acesso não estão disponíveis nos documentos XML de NF-e recebidos.
-   As notas fiscais eletrônicos de exibição que não são lançados, mas recebidos as teclas de acesso para.

Você pode configurar o dynamics 365 para as operações inquiram sobre status das teclas de acesso de NF-e em A SEFAZ várias vezes. Nesse caso, a consulta o último será feito após o tempo que o fornecedor tenha que cancelar um NF-e aprovado término.

## <a name="how-do-i-import-xml-documents-and-danfe-files-from-emails"></a>Como posso importo documentos XML e arquivos de DANFE de email?
Você pode usar ** arquivos XML de email ** a página para importar documentos XML e arquivos de DANFE para documentos de NF-e de email. Antes de importar arquivos, você deve configurar contas de email que são usados para importar documentos XML de NF-e e arquivos de DANFE.

## <a name="can-i-manually-update-the-access-key-for-an-nfe-that-i-didnt-receive-the-xml-document-for"></a>Manualmente que pode atualizar a tecla de acesso para um NFe que eu não recebi o documento XML para?
Sim manualmente, poderá atualizar a tecla de acesso para um NF-e quais você não recebeu XML para o documento. Primeiro você pode gerar a lista de documentos de NF-e das teclas de acesso não estão disponíveis para os documentos XML de NF-e. Para gerar a lista, ** NF-e lançado em 1o ** validação na página, seleciona ** as teclas de acesso não são localizadas em documentos XML recebidos de NF-e ** a opção. Em, ** documentos XML recebidos de NF-e ** na página, atualize a tecla de acesso ** NF-e na chave acesso ** no campo.

## <a name="can-i-post-an-nfe-document-without-validating-the-access-key"></a>Eu pode lançar um documento de NFe sem validar a tecla de acesso?
Sim, você pode lançar um documento de NF-e sem validar a tecla de acesso. Você pode validar as teclas de acesso para esses documentos de NF-e após o lançamento ser concluído. Para gerar uma lista de documentos de NF-e com as teclas de acesso que não forem validadas por ** NF-e SEFAZ, lançado em 1o ** validação na página, seleciona ** status de inquirido SEFAZ não ** a opção. Alternativamente, para lançar somente os documentos eletrônicos fiscais que têm as teclas de acesso validadas por em A SEFAZ, ** os estabelecimentos fiscais **, página ** NF-e federal ** em FastTab **, selecione o lançamento somente NF-e com tecla de acesso válidos ** a opção.

## <a name="how-do-i-inquire-about-the-status-of-nfe-access-keys-at-the-sefaz"></a>Como posso inquiro sobre status das teclas de acesso de NFe? em A SEFAZ
Você pode usar ** consulta recebido XML ** a página para consultar o status das teclas de acesso de NF-e em A SEFAZ. Consultas sobre o status das teclas de acesso serão efetuados várias vezes o NF-e antes que seja aprovado. Adicionalmente, consulta final sobre status que as fizeram depois que a quantidade de tempo que o fornecedor tenha que cancelar um NF-e aprovado término.

## <a name="how-do-i-generate-a-list-of-nfe-documents-that-werent-posted-but-that-i-received-the-xml-documents-for"></a>Como posso gero uma lista de documentos de NFe que não foram lançadas, mas que eu recebi documentos XML para?
Você pode usar ** postado ** a opção ** documentos XML recebidos de NF-e ** página em verificar os documentos de NF-e que não foram lançadas, mas que você recebeu de documentos XML.


