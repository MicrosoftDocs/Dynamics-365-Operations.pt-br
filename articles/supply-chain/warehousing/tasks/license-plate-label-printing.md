---
title: Habilitar a impressão da etiqueta da placa de licença
description: Este tópico mostra como habilitar a impressão automática de um rótulo (SSCC) do código de série do contêiner de remessa depois que o último item for separado do estoque em um processo de trabalho de separação de vendas.
author: perlynne
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d5580edb3324f76f04140bd6793bddaace5fadcf
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977104"
---
# <a name="enable-license-plate-label-printing"></a>Habilitar a impressão da etiqueta da placa de licença

[!include [banner](../../includes/banner.md)]

Este tópico mostra como habilitar a impressão automática de um rótulo (SSCC) do código de série do contêiner de remessa depois que o último item for separado do estoque em um processo de trabalho de separação de vendas. Você pode executar este procedimento na empresa USMF de dados de demonstração. Se sua execução está usando seus próprios dados, você precisa ter uma sequência numérica configurada para matrículas. Será preciso configurar uma impressora de rótulo antes de iniciar a tarefa. Ir para Administração de organização > Configuração > Impressoras de rede. No Painel de Ações, clique em Opções, depois clique no botão de instalação de download do agente de roteiro do documento. Execute o instalador e verifique se você tem uma impressora de rede trabalhando definida como ativa antes de continuar com o procedimento.


## <a name="set-up-the-gs1-company-prefix"></a>Configurar o prefixo da empresa GS1
1. Vá para **Painel de navegação > Módulos > Gerenciamento de depósito > Configuração > Parâmetros de gerenciamento de depósito**.
2. No campo **prefixo da empresa GS1**, insira os 7 números da empresa GS1.
3. Selecione **Salvar**.
4. Feche a página.

## <a name="setup-the-sscc-license-plate-number-sequence"></a>Configuração da sequência numérica de matrícula de SSCC
1. Vá para **Painel de navegação > Módulos > Administração da organização > Sequências numéricas > Sequências numéricas**.
2. No campo **Área**, selecione uma opção.
3. No campo **Referência**, selecione uma opção.
4. No campo **Empresa**, digite um valor.
5. Expanda a seção **Segmentos**.
6. Selecione **Editar**.
7. Na tabela **Segmentos**, selecione a primeira linha
8. Selecione **Remover**.
9. Selecione **Remover**.
10. Selecione **Salvar**.
11. Feche a página.

## <a name="create-the-document-route-layout"></a>Crie o layout de roteiro do documento
1. Vá para **painel de Navegação > Módulos > Gerenciamento de depósito > Configuração > Roteamento de documentos > Layouts de roteamento de documentos**. Habilitar o layout SSCC.  
2. Selecione **Novo**.
3. No campo **ID de Layout**, digite um valor.
4. No campo **Descrição**, digite um valor.
5. Selecione **Inserir no final do texto**.
6. Selecione **Salvar**.
7. Feche a página.

## <a name="set-up-the-document-routing"></a>Configurar o roteamento de documentos
1. Vá para **painel de Navegação > Módulos > Gerenciamento de depósito > Configuração > Roteamento de documentos > Roteamento de documentos**.
2. No campo **Tipo de ordem de serviço**, selecione uma opção.
3. Selecione **Novo**.
4. No campo **Depósito**, digite um valor.
5. No campo **Nome**, digite um valor.
6. Selecione **Novo**.
7. No campo **ID do Layout**, insira ou selecione um valor.
8. No campo **Nome**, digite o nome da impressora que você quer usar.
9. Selecione **Salvar**.
10. Feche a página.

## <a name="create-mobile-device-menu"></a>Criar o menu de dispositivo móvel
1. Vá para **Painel de navegação > Módulos > Gerenciamento de depósito > Configuração > Dispositivo móvel > Itens de menu do dispositivo móvel**.
2. Selecione **Novo**.
3. No campo **Nome do item de menu**, digite um valor.
4. No campo **Título**, digite um valor.
5. No campo **Modo**, selecione uma opção.
6. Selecione **Sim** no campo **Usar trabalho existente**.
7. Selecione **Sim** no campo **Gerar placa de licença**.
8. Expanda a seção **Classes de trabalho**.
9. Selecione **Novo**.
10. No campo **ID da classe de trabalho**, digite um valor.
11. Selecione **Salvar**.
12. Feche a página.
13. Vá para **painel de navegação > Módulos > Gerenciamento de depósito > Configuração > Dispositivo móvel > Menu do dispositivo móvel**.
14. Na árvore, selecione o item de menu que você criou antes.
15. Selecione **Editar**.
16. Selecione a seta para adicionar o item de menu ao menu.
17. Selecione **Salvar**.
18. Feche a página.

## <a name="update-a-work-template"></a>Atualizar um modelo de trabalho
1. Vá para **Painel de navegação > Módulos > Gerenciamento de depósito > Configuração > Trabalho > Modelos de trabalho**.
2. Selecione **Editar**.
3. Selecione **Novo**.
4. No campo **Tipo de trabalho**, selecione **Imprimir**.
5. No campo **ID da classe de trabalho**, insira ou selecione um valor.
6. Selecione **Mover para cima**.
7. Selecione **Salvar**.
8. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]