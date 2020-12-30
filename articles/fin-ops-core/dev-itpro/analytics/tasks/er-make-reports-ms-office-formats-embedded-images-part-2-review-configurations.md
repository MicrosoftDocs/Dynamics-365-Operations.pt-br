---
title: Revisar configurações para criar relatórios em formatos do Office com imagens incorporadas
description: Para concluir essas etapas, primeiro você deve concluir as etapas no guia de tarefas "ER Criar relatórios nos formatos do MS Office com imagens incorporadas (Parte 1 – Configurar parâmetros)".
author: NickSelin
manager: AnnBe
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8c41ff1ba99411b97ea2b5d9f31bdee7c7701315
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684346"
---
# <a name="review-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a>Revisar configurações para criar relatórios em formatos do Office com imagens incorporadas

[!include [banner](../../includes/banner.md)]

Para concluir essas etapas, primeiro você deve concluir as etapas no guia de tarefas "ER Criar relatórios nos formatos do MS Office com imagens incorporadas (Parte 1: Configurar parâmetros)".

Este procedimento mostra como criar configurações de relatório eletrônico (ER) para gerar documentos eletrônicos contendo imagens incorporadas no Microsoft Excel e no Microsoft Word. Neste exemplo, você revisará as configurações de ER para a empresa exemplo, Litware, Inc. 

Esse procedimento é destinado a usuários com a função de Administrador do sistema ou Desenvolvedor de relatório eletrônico. As etapas podem ser concluídas usando o conjunto de dados de USMF.


## <a name="review-the-imported-data-model"></a>Revise o modelo de dados importados
1. Vá para Administração da organização > Relatório eletrônico > Configurações.
2. Na árvore, selecione "Modelo de cheques'.
3. Clique em Designer.
    * Esse modelo é criado para representar cheques de pagamento do ponto de vista comercial e do mapeamento desse modelo para fontes de dados do aplicativo. Examine este modelo através do Designer de operações do ER. Observe os atributos dos elementos do modelo que são apresentados: estrutura, nome, descrição, tipo de dados etc.   
4. Na árvore, expanda 'raiz'.
5. Na árvore, selecione 'raiz\cheques'.
6. Na árvore, expanda 'raiz\cheques'.
7. Na árvore, expanda 'raiz\cheques\atributos'.
8. Na árvore, expanda 'raiz\pagador'.
9. Na árvore, selecione 'raiz\istestrun'.
10. Na árvore, selecione 'raiz\layout'.
    * O elemento do layout deste modelo representa os detalhes do layout de impressão do formulário de cheque da conta bancária selecionada. Também inclui dois nós do tipo de dados de contêiner para armazenar imagens.   
11. Na árvore, expanda 'raiz\layout'.
12. Na árvore, selecione 'raiz\layout\logotipo da empresa'.
13. Na árvore, expanda 'raiz\layout\logotipo da empresa'.
14. Na árvore, selecione 'raiz\layout\logotipo da empresa\imagem'.
15. Na árvore, selecione 'raiz\layout\logotipo da empresa\isprinted'.
16. Na árvore, selecione 'raiz\layout\assinatura'.
17. Na árvore, expanda 'raiz\layout\assinatura'.
18. Na árvore, selecione 'raiz\layout\assinatura\imagem'.
19. Na árvore, selecione 'raiz\layout\assinatura\isprinted'.
    * Observe que dois elementos do modelo de dados de imagem estão associados aos campos das tabelas que contêm imagens do logotipo da empresa e da assinatura da pessoa autorizada no formato binário.  
20. Na árvore, expanda 'raiz\layout\marca d'água'.
21. Clique em Mapear modelo para fonte de dados.
22. Clique em Designer.
23. Na árvore, expanda 'chequesselected'.
24. Na árvore, expanda 'layout'.
25. Na árvore, expanda 'layout\logotipo da empresa'.
26. Na árvore, expanda 'layout\assinatura'.
27. Na árvore, expanda 'layout\marca d'água'.
28. Ative "Mostrar detalhes".
    * Observe que o elemento de modelo de dados de cheques é associado à tabela de TmpChequePrintout que, em tempo de execução, conterá os registros dos cheques que o usuário selecionou para impressão.   
29. Feche a página.
30. Feche a página.
31. Feche a página.

## <a name="review-the-imported-format"></a>Examine o formato importado
1. Na árvore, expanda "Modelo de cheques'.
2. Na árvore, selecione 'Modelo para cheques\Formato de impressão de cheques'.
3. Clique em Designer.
4. Clique em Anexos.
5. Clique em Abrir.
    * Abra o modelo de relatório anexado no Excel.  
    * Revise o modelo de relatório do Excel anexado que será usado para imprimir os cheques. O modelo contém dois cheques por página e é criado para imprimir cheques no formulário pré-impresso. Observe que duas imagens em branco são inseridas. Essas imagens em branco são para o logotipo da empresa e a assinatura da pessoa que está autorizando um pagamento. Verifique que as imagens são denominadas CompLogo e SignatureImage, respectivamente, no Excel.   
6. Feche a página.
7. Na árvore, expanda 'Relatório'.
8. Na árvore, expanda 'Relatório\ChequeLines'.
9. Na árvore, selecione 'Relatório\ChequeLines\CompLogo'.
10. Ative "Mostrar detalhes".
    * Observe que o elemento da célula de formato "CompLogo" representa o item do Excel que é usado para preencher a imagem do logotipo da empresa no relatório. Esse elemento de formato está associado ao elemento de modelo de dados de imagem que, em tempo de execução, contém uma imagem de logotipo da empresa no formato binário.   
11. Clique na aba Mapeamento.
12. Clique em Edição habilitada.
    * Observe que você pode criar o elemento da célula de formato "CompLogo", de modo que ele não seja mais habilitado. Nesse caso, o elemento de imagem associado do Excel ocultará um logotipo da empresa no relatório gerado. Se a expressão habilitada retornar TRUE e a associação definida não mostrar nenhuma imagem, o elemento de imagem associado do Excel mostrará uma imagem que foi salva no modelo do Excel.   
13. Feche a página.
14. Na árvore, expanda “rótulos: Contêiner”.
    * Alguns rótulos que são apresentados no formulário pré-impresso do cheque serão incluídos no relatório quando ele for criado para fins de teste. Entretanto, esses rótulos não serão impressos durante a impressão real porque o formulário pré-impresso já os inclui.  
15. Feche a página.

