---
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 2%

---
# Instruções

**Observação: esta página (ou qualquer página readme.md) não será publicada na documentação voltada para o cliente**

## TOC

+ `TOC.md` na raiz do guia do usuário fornece a organização dos tópicos contidos no guia desta solução.
+ Cada guia do usuário terá seu próprio `TOC.md` exclusivo, no qual você pode ordenar todas as páginas/tópicos, conforme necessário.
+ A primeira página de todos os guias do usuário é `overview.md`.

## Guia do usuário

+ A introdução ao guia do usuário é chamada `overview.md`
+ Cada tópico no guia do usuário tem seu próprio diretório distinto.
   + Se houver um tópico no guia chamado *Implementação*, o diretório correspondente será `/implementation`
+ Todos os ativos de imagem são armazenados em `/assets`, na raiz do guia do usuário.
   + Todas as imagens no diretório `/assets` serão localizadas.
   + Nenhuma imagem no diretório `/no-localize` será localizada (há uma surpresa). Isso pode ser usado para garantir versões in loc que os ativos específicos não serão reproduzidos desnecessariamente.

## Metadados do guia do usuário

+ Os metadados que descrevem o guia do usuário são armazenados no `TOC.md`. Isso inclui:
   + produto - nome do produto/recurso.
   + nuvem - nuvem à qual este produto pertence.
   + público-alvo: público-alvo ou arquétipo no qual o guia é direcionado.
   + guia do usuário - nome do guia do usuário.

## Metadados de página

+ Os metadados necessários para descrever um documento são armazenados como parte de cada página individual. Isso inclui:
   + título - título da página.
   + descrição - descrição da página.
   + título SEO - título alternativo SEO.
   + descrição SEO - título alternativo para fins de SEO.
   + abreviado - (campo opcional).
   + index - sim/não - a página será indexada pela plataforma de pesquisa da Adobe.
   + traduzir - sim/não - essa página será localizada.
   + versão - usada principalmente para AEM e Campaign, para indicar a versão do produto.
   + private-feature-pack - usado principalmente para o AEM.
   + beta - este produto é beta?
   + redirecionar - pode ser usado para criar uma referência para uma nova página, se necessário.
   + doc-type: reference (default) / troubleshooting / developer / tutorial / kb / whitepaper.

## Mais Informações

Para obter mais instruções de publicação, guias de estilos, amostras e outros recursos, visite o [Repositório de documentação colaborativa](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
