---
title: ER Atualize seu formato adotando uma nova versão com base nesse formato
description: As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode manter uma configuração de formato de Relatório eletrônico (RE).
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 17fe6d772040c73959685920743225c128421951
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684250"
---
# <a name="er-upgrade-your-format-by-adopting-a-new-base-version-of-that-format"></a>ER Atualize seu formato adotando uma nova versão com base nesse formato

[!include [banner](../../includes/banner.md)]

As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode manter uma configuração de formato de Relatório eletrônico (RE). Este processo explica como uma versão personalizada de um formato pode ser criada com base no formato recebido de um fornecedor de configuração (CP). Também explica como adotar uma nova versão de base desse formato.

Para executar estas etapas, primeiro você deve concluir as etapas "Criar um provedor de configuração e marcá-lo como ativo" e procedimentos "Usar o formato criado para gerar documentos eletrônicos para os pagamentos". Essas etapas podem ser executadas na empresa GBSI.

## <a name="select-format-configuration-for-customization"></a>Selecione a configuração de formato para a personalização
1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.

    Neste exemplo, a empresa exemplo, Litware, Inc. (https://www.litware.com), atuará como um provedor de configuração que oferece suporte a configurações de formato para pagamentos eletrônicos de um país específico.    A empresa exemplo, Proseware, Inc (http://www.proseware.com), atuará como um consumidor da configuração do formato fornecida pela Litware, Inc. A Proseware, Inc. usa formatos em determinadas regiões desse país.  
2. Clique em Configurações de relatórios.
3. Clique em Mostrar filtros.
4. Aplique os seguintes filtros: insira um valor de filtro de "BACS (fictício do Reino Unido)", no campo "Nome" usando o operador de filtro "começa com".
  
    A configuração de formato selecionada BACS (fictício do Reino Unido) pertence ao fornecedor Litware, Inc.  

5. Clique em Mostrar filtros.
6. Na lista, localize e selecione o PDV desejado.

    A versão do formato com o status de Concluído será usada pela Proseware, Inc. para personalização.  

## <a name="create-a-new-configuration-for-your-custom-format-of-electronic-document"></a>Crie uma nova configuração para o formato de documento personalizado eletrônico
A Proseware, Inc. recebeu a configuração da versão 1.1 de BACS (fictício do Reino Unido) que contém o formato inicial para gerar documentos de pagamento eletrônico da Litware, Inc. em conformidade com a subscrição de serviço. A Proseware, Inc. deseja começar a usá-la como um padrão para seu país, mas algumas personalizações são necessárias para oferecer suporte a requisitos regionais específicos. A Proseware, Inc. também deseja manter a capacidade de atualizar um formato personalizado assim que uma nova versão dele (com alterações para oferecer suporte a novos requisitos específicos do país) venha da Litware, Inc. e desejam fazer essa atualização com o menor custo possível.  

Para isso, a Proseware, Inc. precisa criar uma configuração usando configuração BACS (fictício do Reino Unido) da Litware, Inc. como base.  

1. Feche a página.
2. Selecione a Proseware, Inc. para torná-la um provedor ativo.
3. Clique em Definir como ativo.
4. Clique em Configurações de relatórios.
5. Na árvore, expanda "Pagamentos (modelo simplificado)".
6. Na árvore, selecione "Pagamentos (modelo simplificado)\BACS (Reino Unido fictício)".

    Selecione a configuração BACS (fictício do Reino Unido) da Litware, Inc. A Proseware, Inc. usará a versão 1.1 como uma base para a versão personalizada.  

7. Clique em Criar configuração para abrir a caixa de diálogo suspensa.

    Isso permite criar uma nova configuração para um formato de pagamento personalizado.  

8. No campo Novo, insira "Derivar do Nome: BACS (fictício do Reino Unido), Litware, Inc.'.

    Selecione Opção de derivação para confirmar o uso de BACS (fictício do Reino Unido) como base para criar a versão personalizada.  

9. No campo Nome, digite 'BACS (Reino Unido personalizado)'.
10. No campo Descrição, digite "Formato de pagamento de fornecedor BACS (personalizado fictício do Reino Unido)".

    O provedor de configuração ativo (Proseware, Inc.) é automaticamente inserido aqui. Este provedor será capaz de manter essa configuração. Outros provedores podem usar esta configuração, mas não poderão mantê-la.  

11. Clique em Criar configuração.

## <a name="customize-your-format-for-the-electronic-document"></a>Personalizar o formato do documento eletrônico
1. Clique em Designer.
2. Clique em Expandir/recolher.
3. Clique em Expandir/recolher.
4. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco".
5. Clique em Adicionar para abrir a caixa de diálogo suspensa.
6. Na árvore, selecione 'XML\Elemento'.
7. No campo Nome, digite 'IBAN'.
8. Clique em OK.
9. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco\IBAN".
10. Clique em Adicionar para abrir a caixa de diálogo suspensa.
11. Na árvore, selecione 'Texto\Cadeia de caracteres'.
12. Clique em OK.
13. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Nome\String".
14. No campo Comprimento máximo, insira "60".
15. Clique na aba Mapeamento.
16. Na árvore, expanda 'modelo'.
17. Na árvore, expanda 'modelo\Pagamentos'.
18. Na árvore, expanda 'modelo\Pagamentos\Credor'.
19. Na árvore, expanda 'modelo\Pagamentos\Credor\Conta'.
20. Na árvore, selecione "modelo\Pagamentos\Credor\Conta\IBAN".
21. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item = modelo.Pagamentos\Fornecedor\Banco\IBAN\String".
22. Clique em Associar.
23. Clique em Salvar.

## <a name="validate-the-customized-format"></a>Validar o formato personalizado
1. Clique em Validar.

    Valide o layout do formato personalizado e as alterações de projeção de dados para garantir que todas as associações são aprovadas.  

2. Feche a página.

## <a name="change-the-status-of-the-current-version-of-the-custom-format-configuration"></a>Alterar o status da versão atual da configuração de formato personalizado
Altere o status da configuração do formato criado de Rascunho para Concluído para torná-lo disponível e gerar documentação de pagamento.  

1. Clique em Alterar status.

    Observe que a versão atual da configuração selecionada está no status Rascunho.  

2. Clique em Concluir.
3. No campo Descrição, digite um valor.
4. Clique em OK.
5. Na lista, localize e selecione o PDV desejado.

    Observe que a configuração criada será salva como versão 1.1.1 concluída. Isso significa que é a versão 1 do formato de costume BACS (personalizado fictício do Reino Unido), que se baseia na versão 1 do formato de BACS (fictício do Reino Unido), que se baseia na versão 1 do modelo de dados de pagamentos (modelo simplificado).  

## <a name="test-the-customized-format-to-generate-payment-files"></a>Testar o formato personalizado para gerar arquivos de pagamento
Conclua as etapas no procedimento "Usar formato criado para gerar documentos eletrônicos para pagamentos" em uma sessão do Finance and Operations paralela. Selecione o formato BACS (personalizado fictício do Reino Unido) nos parâmetros de método de pagamento eletrônico. Verifique se o arquivo de pagamento criado contém o nó recentemente introduzido ao XML que apresenta o código de IBAN no acordo das exigências regionais.  

## <a name="update-the-existing-country-specific-configuration"></a>Atualizar a configuração específica existente do país
A Litware, Inc. precisa atualizar a configuração BACS (fictício do Reino Unido) e adotar novos requisitos de país para o gerenciamento do formato do documento eletrônico. Posteriormente, isso será incluído em uma nova versão dessa configuração que será oferecida para assinantes de serviço, incluindo Proseware, Inc.  

Nos processos relacionados de provisão de serviço reais, cada nova versão de BACS (fictício do Reino Unido) pode ser importada pela Proseware, Inc. do repositório LCS das configurações da Litware, Inc. Nesse procedimento, simularemos isso atualizando BACS (fictício do Reino Unido) em nome de um prestador de serviço.  

1. Feche a página.
2. Selecione o fornecedor "Litware, Inc.".
3. Clique em Definir como ativo.
4. Clique em Configurações de relatórios.
5. Na árvore, expanda "Pagamentos (modelo simplificado)".
6. Na árvore, selecione "Pagamentos (modelo simplificado)\BACS (Reino Unido fictício)".

    A versão de rascunho de propriedade do provedor BACS (fictício do Reino Unido) da Litware, Inc. é selecionada para trazer alterações para oferecer suporte aos requisitos específicos do país.  

## <a name="localize-the-base-format-of-the-electronic-document"></a>Localizar o formato base do documento eletrônico
Suponha que haja novos requisitos específicos de país a serem suportados pela Litware, Inc.:  

- Um valor para o código SWIFT do banco credor em cada transação de pagamento.
- Um limite de 100 caracteres para o comprimento do texto para o nome do fornecedor no arquivo de geração.  
- Novos requisitos específicos do país  
- Selecione a versão de rascunho de configuração selecionada para apresentar alterações necessárias.  


1. Clique em Designer.
2. Clique em Expandir/recolher.
3. Clique em Expandir/recolher.
4. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco".
5. Clique em Adicionar para abrir a caixa de diálogo suspensa.
6. Na árvore, selecione 'XML\Elemento'.
7. No campo Nome, digite 'SWIFT'.
8. Clique em OK.
9. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco\SWIFT".
10. Clique em Adicionar para abrir a caixa de diálogo suspensa.
11. Na árvore, selecione 'Texto\Cadeia de caracteres'.
12. Clique em OK.
13. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Nome\String".
14. No campo Comprimento máximo, insira "100".
15. Clique na aba Mapeamento.
16. Na árvore, expanda 'modelo'.
17. Na árvore, expanda 'modelo\Pagamentos'.
18. Na árvore, expanda 'modelo\Pagamentos\Credor'.
19. Na árvore, expanda 'modelo\Pagamentos\Credor\Agente'.
20. Na árvore, selecione "modelo\Pagamentos\Credor\Agente\SWIFT".
21. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item = modelo.Pagamentos\Fornecedor\Banco\SWIFT\String".
22. Clique em Associar.
23. Clique em Salvar.

## <a name="validate-the-localized-format"></a>Validar o formato localizado
1. Clique em Validar.
2. Feche a página.

## <a name="change-the-status-of-the-current-version-of-the-base-format-configuration"></a>Altere o status da versão atual da configuração do formato base
Altere o status da configuração básica atualizada no formato de Rascunho para Concluído para tornar disponível a geração de documentos do pagamento e de atualizações das configurações do formato derivadas dela.  

1. Clique em Alterar status.

    Observe que a versão atual da configuração selecionada está no status Rascunho.  

2. Clique em Concluir.
3. No campo Descrição, digite um valor.
4. Clique em OK.
5. Na lista, localize e selecione o PDV desejado.

## <a name="change-the-base-version-for-the-custom-format-configuration"></a>Versão da alteração para a configuração do formato personalizado

A Proseware, Inc. é informada que uma nova versão 1.2 da configuração BACS (fictício do Reino Unido) está disponível para gerar documentos de pagamento eletrônico de acordo com os novos requisitos específicos anunciados. A Proseware, Inc. deseja começar a usá-la como padrão para o país.  

Para isso, a Proseware, Inc. precisa alterar a versão da configuração base para a configuração personalizada BACS (Reino Unido fictício personalizado). Em vez da versão 1.1 de BACS (fictício do Reino Unido) use a nova versão 1.2.  

1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
2. Selecione o provedor da Proseware, Inc. para marcá-lo como ativo.
3. Clique em Definir como ativo.
4. Clique em Configurações de relatórios.
5. Na árvore, expanda "Pagamentos (modelo simplificado)".
6. Na árvore, expanda "Pagamentos (modelo simplificado)\BACS (Reino Unido fictício)".
7. Na árvore, selecione "Pagamentos (modelo simplificado)\BACS (Reino Unido fictício)\BACS (Reino Unido personalizado fictício)".

    Selecione a configuração de BACS (personalizado fictício do Reino Unido), que pertence ao Proseware, Inc.  

    Use a versão de rascunho de configuração selecionada para apresentar alterações necessárias.  

8. Clique em Trocar base.

    Selecione a nova versão 1.2 da configuração base a ser aplicada como uma nova base para atualização da configuração.  

9. Clique em OK.

    Observe que alguns conflitos foram descobertos entre mesclar a versão personalizada e uma nova versão base que representam as alterações do formato que não podem ser mescladas automaticamente.  

## <a name="resolve-rebase-conflicts"></a>Resolver conflitos de rebase
1. Clique em Designer.
    
    Observe que as alterações no limite do tamanho do texto do nome do fornecedor não podem ser resolvidas automaticamente. Consequentemente, é apresentado em uma lista de conflitos. Para cada conflito do tipo Atualização, as opções a seguir estão disponíveis: – aplicar um valor de base anterior (botão no topo da grade) para trazer o valor da versão base anterior (0 em nosso caso).  - Aplicar um valor de base (botão no topo da grade) para trazer no novo valor da versão base (100 em nosso caso).  - Mantenha seu próprio valor (personalizado) (60 em nosso caso).  Clique em aplica o valor de base para a aplicação do limite do país específico de 100 caracteres de comprimento de texto para nomes do fornecedor.  

    Observe que a Proseware, Inc. e a Litware, Inc. têm versões personalizadas e locais deste formato usando códigos IBAN e SWIFT com componentes relacionados que são automaticamente mesclados no formato gerenciado.  

2. Clique em Aplicar valor base.

    Clique em Aplicar o valor de base para aplicar o limite do país específico de 100 caracteres para os nomes dos fornecedores.  

3. Clique em Salvar.

    Salvar o formato removerá conflitos resolvidos da lista de conflitos.  

4. Feche a página.

## <a name="change-the-status-of-the-new-version-of-the-custom-format-configuration"></a>Altere o status da versão nova da configuração do formato personalizado
1. Clique em Alterar status.

    Altere o status da configuração atualizada, formato personalizado de Rascunho para Concluído. Isso criará a configuração de formato disponível para a geração de documentos de pagamento. Observe que a versão atual da configuração selecionada está no status Rascunho.  

2. Clique em Concluir.
3. No campo Descrição, digite um valor.
4. Clique em OK.

    Observe que a configuração criada é salva como uma versão completa 1.2.2: versão 2 do formato da base BACS (personalizado fictício do Reino Unido), que é baseado na versão 2 do formato da base BACS (fictício do Reino Unido), que é baseada na versão 1 do modelo de dados de Pagamentos (modelo simplificado).  

## <a name="test-the-customized-format-for-payment-files-generation"></a>Teste o formato personalizado para gerar arquivos de pagamento
Conclua as etapas no procedimento "Usar formato criado para gerar documentos eletrônicos para pagamentos" em uma sessão do Finance and Operations paralela. Selecione o "Formato BACS criado (personalizado fictício do Reino Unido)" nos parâmetros de método de pagamento eletrônico. Verifique se o arquivo de pagamento criado contém o nó XML recentemente introduzido pela Proseware, Inc. que apresenta o código de conta IBAN de acordo com as exigências regionais. O arquivo também deve conter o nó XML introduzido recentemente pela Litware, Inc. que apresenta o código bancário SWIFT de acordo os requisitos do país.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]