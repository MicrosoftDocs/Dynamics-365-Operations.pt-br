---
title: Habilitar a impressão da etiqueta da placa de licença
description: Este procedimento permite a impressão automática de um rótulo (SSCC) do código de série do contêiner de remessa depois que o último item é separado do estoque em um processo de trabalho de separação de vendas.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ed74806e5e037570f3ed7f59725eed494c829d34
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1847249"
---
# <a name="enable-license-plate-label-printing"></a>Habilitar a impressão da etiqueta da placa de licença

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento permite a impressão automática de um rótulo (SSCC) do código de série do contêiner de remessa depois que o último item é separado do estoque em um processo de trabalho de separação de vendas. Você pode executar este procedimento na empresa USMF de dados de demonstração. Se sua execução está usando seus próprios dados, você precisa ter uma sequência numérica configurada para matrículas. Será preciso configurar uma impressora de rótulo antes de iniciar a tarefa. Ir para Administração de organização > Configuração > Impressoras de rede. No painel de ações, clique em Opções, depois clique no botão de instalação de download do agente de roteiro do documento. Execute o instalador e verifique se você tem uma impressora de rede trabalhando definida como ativa antes de continuar com o procedimento.


## <a name="set-up-the-gs1-company-prefix"></a>Configurar o prefixo da empresa GS1
1. Vá para Gerenciamento de depósito > Configuração > Parâmetros de gerenciamento de depósito.
2. No campo prefixo da empresa GS1, insira os 7 números do número de sua empresa GS1.
3. Clique em Salvar.
4. Feche a página.

## <a name="setup-the-sscc-license-plate-number-sequence"></a>Configuração da sequência numérica de matrícula de SSCC
1. Vá para Administração da organização > Sequências numéricas > Sequências numéricas.
2. No campo Área, selecione uma opção.
3. No campo Referência, selecione uma opção.
4. No campo Empresa, digite um valor.
5. Na lista, marque a linha selecionada.
6. Na lista, clique no link na linha selecionada.
7. Expandir a seção Segmentos.
8. Clique em Editar.
9. Na tabela Segmentos, selecione a primeira linha
10. Clique em Remover.
11. Clique em Remover.
12. Clique em Salvar.
13. Feche a página.

## <a name="create-the-document-route-layout"></a>Crie o layout de roteiro do documento
1. Vá para Gerenciamento de depósito > Configuração > Roteiro de documento > Layouts de roteiro de documento.
    * Habilitar o layout SSCC.  
2. Clique em Novo.
3. No campo ID de layout, digite um valor.
4. No campo Descrição, digite um valor.
5. Na lista, localize e selecione o PDV desejado.
6. Clique em Inserir no final do texto.
7. Clique em Salvar.
8. Feche a página.

## <a name="set-up-the-document-routing"></a>Configurar o roteamento de documentos
1. Vá para Gerenciamento de depósito > Configuração > Roteiro de documento > Roteiro de documento.
2. No campo Tipo de ordem de trabalho, selecione uma opção.
3. Clique em Novo.
4. No campo Depósito, digite um valor.
5. No campo Nome, digite um valor.
6. Clique em Novo.
7. No campo ID de layout, insira ou selecione um valor.
8. No campo Nome, insira o nome da impressora que deseja usar.
9. Clique em Salvar.
10. Feche a página.

## <a name="create-mobile-device-menu"></a>Criar o menu de dispositivo móvel
1. Vá para Gerenciamento de depósito > Configuração > Dispositivo móvel > Itens de menu de dispositivo móvel.
2. Clique em Novo.
3. No campo Item de menu, digite um valor.
4. No campo Título, digite um valor.
5. No campo Modo, selecione uma opção.
6. Selecione Sim no campo Usar trabalho existente.
7. Selecione Sim no campo Gerar placa de licenciamento.
8. Expanda a seção Classes de trabalho.
9. Clique em Novo.
10. No campo ID de classe de trabalho, digite um valor.
11. Clique em Salvar.
12. Feche a página.
13. Vá para Gerenciamento de depósito > Configuração > Dispositivo móvel > Menu de dispositivo móvel.
14. Na lista, localize e selecione o PDV desejado.
15. Na árvore, selecione 'Na árvore, selecione o item de menu que você criou antes'.
16. Clique em Editar.
17. Clique na seta para adicionar o item de menu ao menu.
18. Clique em Salvar.
19. Feche a página.

## <a name="update-a-work-template"></a>Atualizar um modelo de trabalho
1. Vá para Gerenciamento de depósito > Configuração > Trabalho > Modelos de trabalho.
2. Na lista, localize e selecione o PDV desejado.
3. Clique em Editar.
4. Clique em Novo.
5. Na lista, marque a linha selecionada.
6. No campo Tipo de trabalho, selecione 'Imprimir'.
7. No campo ID de classe de trabalho, insira ou selecione um valor.
8. Na lista, clique no link na linha selecionada.
9. Clique em Mover para cima.
10. Clique em Salvar.
11. Feche a página.

