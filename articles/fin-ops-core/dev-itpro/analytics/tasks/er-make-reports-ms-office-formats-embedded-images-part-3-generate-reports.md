---
title: Gerar relatórios em formato do Office com imagens incorporadas
description: Este artigo descreve como criar configurações de relatório eletrônico (ER) para gerar documentos eletrônicos no Excel e Word que contenham imagens incorporadas.
author: kfend
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dfd4aca1013d7fdf408f9057810feedc4b44e586
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290264"
---
# <a name="generate-reports-in-office-format-that-have-embedded-images"></a>Gerar relatórios em formato do Office com imagens incorporadas

[!include [banner](../../includes/banner.md)]

As etapas a seguir explicam como um usuário no papel de "Administrador do Sistema" ou "Desenvolvedor de relatório eletrônico" pode criar configurações de Relatório Eletrônico (RE) para gerar os documentos eletrônicos nos formatos do MS Office (Excel e Word) que contenham imagens incorporadas.

Neste exemplo, você usará as configurações de ER criadas para a empresa exemplo, "Litware, Inc.".  Para completar essas etapas, primeiro você deve concluir as etapas no guia de tarefas "ER Fazer relatórios nos formatos do MS Office com imagens incorporadas (Parte 2: Revisar configurações)". Essas etapas podem ser executadas na empresa "USMF".


## <a name="run-format-with-initial-model-mapping"></a>Executar formato com mapeamento de modelo inicial
1. Acesse Gerenciamento de caixa e bancos > Contas bancárias > Contas bancárias.
2. Use o Filtro Rápido para filtrar o campo Conta bancária com o valor 'USMF OPER'.
3. No Painel de Ação, clique em Configurar.
4. Clique em Verificar.
5. Clique em Imprimir teste.
    * Execute o formato para fins de teste.  
6. Selecione Sim no campo Formato de cheque negociável.
7. Clique em OK.
    * Revise a saída criada. O logotipo da empresa é mostrado no relatório, bem como a assinatura da pessoa autorizada. A imagem de assinatura é obtida do campo do tipo de dados "Contêiner" do registro de layout de cheque que é associado à conta bancária selecionada.  
8. Expanda a seção Cópias.
9. Clique em Editar.
10. No campo Marca d'água, insira "Imprimir marca d'água como Nula".
    * Modificar a configuração do layout de marca d'água para exibir o texto de marca d'água ao gerar o documento de um elemento do Excel.  
11. Clique em Imprimir teste.
12. Clique em OK.
    * Revise a saída criada. A marca-d'água é mostrada no relatório criado, de acordo a opção de seleção.  
13. Feche a página.
14. No Painel de Ação, clique em Gerenciar pagamentos.
15. Clique em Cheques.
16. Clique em Mostrar filtros.
17. Aplique os seguintes filtros: insira um valor de filtro de "381","385","389" no campo "Número do cheque" usando o operador de filtro "é um de".
18. Na lista, marque todas as linhas.
19. Clique em Imprimir cópia de cheque.
    * Execute o formato para reimprimir os cheques selecionados.  
    * Revise a saída criada. Os cheques selecionados foram reimpressos. O logotipo e os rótulos empresariais não são impressos de saída, já que são apresentados no formulário pré-impresso.  

## <a name="modify-the-mapping-of-the-imported-data-model"></a>Modifique mapeamento do modelo de dados importados
1. Feche a página.
2. Feche a página.
3. Acesse Administração da organização > Relatório eletrônico > Configurações.
4. Na árvore, selecione "Modelo de cheques'.
5. Clique em Designer.
6. Clique em Mapear modelo para fonte de dados.
7. Clique em Designer.
    * Alteraremos a associação do item de assinatura do modelo de dados para obter a imagem de assinatura do arquivo que foi anexada ao registro de layout de cheque que está associado à conta bancária selecionada.  
8. Desative Mostrar detalhes.
9. Na árvore, expanda 'layout'.
10. Na árvore, expanda 'layout\assinatura'.
11. Na árvore, selecione 'layout\assinatura\imagem = chequesaccount.'<Relations'.BankChequeLayout.Signature1Bmp'.
12. Na árvore, expanda 'chequesaccount'.
13. Na árvore, expanda 'chequesaccount\<Relações'.
14. Na árvore, expanda 'chequesaccount\<Relações\BankChequeLayout'.
15. Na árvore, expanda 'chequesaccount\<Relações\BankChequeLayout\<Relações'.
16. Na árvore, expanda 'chequesaccount\<Relações\BankChequeLayout\<Relações\<Documentos'.
17. Na árvore, selecione 'chequesaccount\<Relações\BankChequeLayout\<Relações\<Documentos\getFileContentAsContainer()'.
18. Clique em Associar.
19. Clique em Salvar.
20. Feche a página.
21. Feche a página.
22. Feche a página.
23. Feche a página.

## <a name="run-format-using-the-adjusted-model-mapping"></a>Execute o formato usando o mapeamento de modelo ajustado
1. Acesse Gerenciamento de caixa e bancos > Contas bancárias > Contas bancárias.
2. Use o Filtro Rápido para localizar registros. Por exemplo, filtre o campo Conta bancária com um valor de 'USMF OPER'.
3. No Painel de Ação, clique em Configurar.
4. Clique em Verificar.
5. Clique em Imprimir teste.
6. Clique em OK.
    * Revise a saída criada. A imagem do anexo de Gerenciamento de documentos é exibida como a assinatura de uma pessoa autorizada.  

## <a name="use-ms-word-document-as-a-template-in-the-imported-format"></a>Use o documento do Word MS como um modelo no formato importado
1. Feche a página.
2. Feche a página.
3. Acesse Administração da organização > Relatório eletrônico > Configurações.
4. Na árvore, expanda "Modelo de cheques'.
5. Na árvore, selecione 'Modelo para cheques\Formato de impressão de cheques'.
6. Clique em Designer.
7. Clique em Anexos.
8. Clique em Excluir.
9. Clique em Sim.
10. Clique em Novo.
11. Clique em Arquivo.
    * Clique em Pesquisar e selecione o arquivo baixado previamente "Cheque template Word.docx".  
12. Feche a página.
13. No campo Modelo, insira ou selecione um valor.
14. Clique em Salvar.
15. Feche a página.
16. Clique em Editar.
17. Selecione Sim no campo Executar Rascunho.
18. Feche a página.
19. Acesse Gerenciamento de caixa e bancos > Contas bancárias > Contas bancárias.
20. Use o Filtro Rápido para filtrar o campo Conta bancária com o valor 'USMF OPER'.
21. Clique em Verificar.
22. Clique em Imprimir teste.
23. Clique em OK.
    * Revise a saída criada. A saída foi gerada como um documento do Word com imagens incorporadas apresentando o logotipo da empresa, a assinatura de uma pessoa autorizada e o texto selecionado da marca d'água.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
