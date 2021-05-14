---
title: Criar configurações para gerar relatórios em formatos do Office com imagens incorporadas
description: Este tópico descreve como criar configurações de relatório eletrônico (ER) que gerem documentos eletrônicos nos formatos Excel e Word que contenham imagens incorporadas.
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5eea178a351716425706f481ae66c5b5183a52e5
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944548"
---
# <a name="design-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a>Criar configurações para gerar relatórios em formatos do Office com imagens incorporadas

[!include [banner](../../includes/banner.md)]

Para concluir as etapas neste procedimento, você deve primeiro concluir o procedimento, "ER Criar um provedor de configuração e marcá-lo como ativo". Este procedimento explica como criar configurações de relatório eletrônico (ER) para gerar um documento do Microsoft Excel ou do Word contendo imagens incorporadas. Nesse procedimento, você criará as configurações de ER necessárias para a empresa de exemplo, a Litware, Inc. Essas etapas podem ser concluídas usando o conjunto de dados USMF. Este procedimento é criado para usuários com a função atribuída de administrador do sistema ou desenvolvedor de relatório eletrônico. Antes de começar, baixe e salve os seguintes arquivos: 

| Descrição                                          | Nome do arquivo                   |
|------------------------------------------------------|-----------------------------|
| Configuração do modelo de dados de ER                          | [Modelo para cheques.xml](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)       |
| Configuração de formato ER                              | [Formato de impressão de cheques.xml](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |
| Imagem do logotipo da empresa                                   | [Company logo.png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png)            |
| Imagem de assinatura                                      | [Signature image.png](https://download.microsoft.com/download/5/0/9/509151b3-06fc-4870-9408-7c9a43b72771/Signatureimage.png)         |
| Imagem de assinatura alternativa                          | [Signature image 2.png](https://download.microsoft.com/download/3/0/0/30045bf1-0ff6-4215-9162-b77c2f5dcc7c/Signatureimage2.png)       |
| Modelo do Microsoft Word para imprimir cheques de pagamento  | [Cheque template Word.docx](https://download.microsoft.com/download/4/4/d/44d9d255-9ad1-42fe-87db-23f319fd8e89/ChequetemplateWord.docx)   |

## <a name="verify-prerequisites"></a>Verificar pré-requisitos  
 1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.  
 2. Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como Ativo. Se não visualizar este provedor de configuração, conclua as etapas no procedimento "Criar um provedor de configuração e marcá-lo como ativo".   
 3. Clique em Configurações de relatórios.  
 
## <a name="add-a-new-er-model-configuration"></a>Adicionar uma nova configuração de modelo de ER  
 1. Em vez de criar um novo modelo, você pode carregar o arquivo de configuração do modelo de ER (Model for cheques.xml) que salvou anteriormente. Este arquivo contém o modelo de dados de amostra para cheques de pagamento e o mapeamento do modelo de dados para os componentes de dados do aplicativo Dynamics 365 for Operations.   
 2. Na Guia Rápida Versões, clique em Troca.   
 3. Clique em Carregar de um arquivo XML.  
 4. Clique em Procurar e selecione Model for cheques.xml.   
 5. Clique em OK.  
 6. O modelo carregado será usado como fonte de dados de informações para gerar documentos que contenham imagens no Excel e no Word.  

## <a name="add-a-new-er-format-configuration"></a>Adicionar uma nova configuração de formato de ER  
 1. Em vez de criar um novo formato, você pode carregar o arquivo de configuração do formato de ER (Cheques printing format.xml) que salvou anteriormente. Esse arquivo contém o layout de exemplo do formato para imprimir cheques usando o formulário pré-impresso e o mapeamento desse formato para o modelo de dados "Modelo de cheques".   
 2. Clique em Trocar.  
 3. Clique em Carregar de um arquivo XML.  
 4. Clique em Procurar e selecione o arquivo Cheques printing format.xml.   
 5. Clique em OK.  
 6. Na árvore, expanda "Modelo de cheques'.  
 7. Na árvore, selecione 'Modelo para cheques\Formato de impressão de cheques'.  
 8. O formato carregado será usado para gerar documentos que contenham imagens no Excel e no Word.   

## <a name="configure-er-user-parameters"></a>Configurar parâmetros de usuário de ER  
 1. No Painel de Ação, clique em Configurações.  
 2. Clique em Parâmetros de usuário.  
 3. Selecione Sim no campo Executar configurações.  
  Ative o sinalizador "Executar rascunho" para iniciar a versão de rascunho do formato selecionado em vez da versão concluída.  
 4. Clique em OK.  

## <a name="configure-cash--bank-management-parameters"></a>Configurar parâmetros de gerenciamento de banco e caixa  
 1. Vá para Gerenciamento de caixa e bancos > Contas bancárias > Contas bancárias.  
 2. Use o Filtro Rápido para filtrar o campo Conta bancária com o valor 'USMF OPER'.  
 3. No Painel de Ação, clique em Configurar.  
 4. Clique em Verificar.  
 5. Expandir a seção Instalação.  
 6. Clique em Editar.  
 7. Selecione Sim no campo Logotipo da empresa.  
 8. Clique em Logotipo da empresa.  
 9. Clique em Alterar.  
 10. Clique em Procurar e selecione o arquivo baixado anteriormente, Company logo.png.   
 11. Clique em Salvar.  
 12. Feche a página.  
 13. Expanda a seção Assinatura.  
 14. Selecione Sim no campo Imprimir primeira assinatura.  
 15. Clique em Alterar.  
 16. Clique em Procurar e selecione o arquivo baixado anteriormente, Signature image.png.   
 17. Expanda a seção Cópias.  
 18. No campo Marca d'água, selecione uma opção.  
 19. Selecione Sim no campo Formato de exportação eletrônico genérico.  
 20. Selecione a configuração 'Formulário de impressão de cheques'.  
 21. Agora o formato de ER selecionado será usado para a impressão de cheques.  
 22. Clique em Anexar.  
 23. Clique em Novo.  
 24. Clique em Arquivo.  
 25. Clique em Procurar e selecione o arquivo baixado anteriormente, Signature image 2.png.   
 26. Feche a página.  
 27. Feche a página.  
 28. Feche a página.  
 29. Vá para Gerenciamento de dinheiro e banco > Configuração > Parâmetros do gerenciamento de dinheiro e banco.  
 30. Selecione Sim no campo Permitir a criação do pré-registro em contas bancárias inativas:.  
 31. Clique em Salvar.  
 32. Feche a página.  


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
