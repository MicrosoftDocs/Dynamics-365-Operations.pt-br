---
title: Gerar documentos com dados da solicitação de emprego
description: Para concluir as etapas desse procedimento, você deve primeiramente concluir o procedimento, "ER, gerar documentos com atualização de dados de aplicativo (Parte 4 – Modificar formato)".
author: kfend
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e0f4fe5c948d1d6ea7c306a37d629c6e381dbd00
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290444"
---
# <a name="generate-documents-that-have-application-data"></a>Gerar documentos com dados do aplicativo

[!include [banner](../../includes/banner.md)]

Para concluir as etapas desse procedimento, você deve primeiramente concluir o procedimento, "ER Gerar documentos com atualização de dados de aplicativo (Parte 4: Modificar formato)".



As etapas desse procedimento explicam como criar configurações de Relatório eletrônico (ER) para gerar um documento eletrônico e atualizar os dados do aplicativo. Nesse procedimento, você executa a configuração de formato de ER para gerar dados de aplicativo de atualização e de relatório Intrastat para arquivar detalhes do processo de relatório.



Este procedimento é criado para usuários com a função atribuída de administrador do sistema ou desenvolvedor de relatório eletrônico. Estas etapas podem ser concluídas usando o conjunto de dados de DEMF. Antes de começar, verifique se o contexto de país para a empresa de DEMF é BEL (Bélgica).


## <a name="set-up-foreign-trade-parameters"></a>Configurar parâmetros de comércio exterior
1. Acesse Imposto > Configuração > Comércio exterior > Parâmetros de comércio exterior.
2. Clique na aba Sequências numéricas.

    Arquivando detalhes de processo de relatório Intrastat, precisamos identificar registros de cada arquivo morto que criamos. Uma sequência numérica especial deve ser configurada para isso.  

3. Selecione a referência "ID de arquivo morto Intrastat".
4. No campo Número, selecione campo Código, digite um valor.

    No campo "Código de sequência numérica", digite ou selecione o valor "Fore_2".  

5. Altera o código de sequência numérica
6. Clique em Salvar.
7. Feche a página.

## <a name="run-modified-er-format"></a>Execute o formato de ER modificado
1. Acesse Administração da organização > Relatório eletrônico > Configurações.
2. Na árvore, expanda 'Intrastat (model)'.
3. Na árvore, selecione 'Intrastat (modelo)\Intrastat (formato)'.
4. Clique em Executar.
5. No campo Inserir nome do arquivo, digite 'intrastat2.xml'.
6. Clique em OK.

## <a name="review-er-format-executions-results"></a>Revise os resultados de execução de formato do ER
Revise o arquivo XML gerado.  
1. Feche a página.
2. Acesse Imposto > Declarações > Comércio exterior > Intrastat.

    Abra este formulário que contém as transações Intrastat que foram incluídas no documento eletrônico gerado.  

3. Clique em Arquivo morto Intrastat.

    Como o formato de ER executado agora contém configurações para a atualização de dados do aplicativo, os detalhes de relatório Intrastat concluído não foram arquivados. Neste formulário, você pode consultar o registro de cabeçalho do arquivo-morto criado.  

4. Clique em Detalhes.

    Neste formulário, você pode consultar os detalhes do arquivo-morto criado.  

5. Feche a página.
6. Feche a página.
7. Feche a página.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
