# Principais Funcionalidades Introduzidas no Java 8

Bem-vindo ao repositório sobre as novidades do Java 8! Este README apresenta uma visão geral profissional das principais funcionalidades introduzidas no Java 8 (JDK 8), lançado em março de 2014. Essas inovações modernizaram a linguagem, tornando-a mais concisa, funcional e eficiente.

O foco está nas mudanças mais impactantes e utilizadas no dia a dia de desenvolvedores. Para detalhes adicionais sobre funcionalidades específicas ou menores, consulte a documentação oficial da Oracle ou contribua com este repositório.

## Sumário
- [1. Expressões Lambda](#1-expressões-lambda-lambda-expressions)
- [2. Referências a Métodos](#2-referências-a-métodos-method-references)
- [3. Métodos Default em Interfaces](#3-métodos-default-em-interfaces-default-methods)
- [4. Métodos Estáticos em Interfaces](#4-métodos-estáticos-em-interfaces-static-methods-in-interfaces)
- [5. API de Streams](#5-api-de-streams-stream-api)
- [6. Classe Optional](#6-classe-optional-optional-class)
- [7. Nova API de Data e Hora](#7-nova-api-de-data-e-hora-date-and-time-api)
- [8. Motor JavaScript Nashorn](#8-motor-javascript-nashorn-nashorn-javascript-engine)
- [9. Anotações Repetíveis e em Tipos](#9-anotações-repetíveis-e-em-tipos-repeating-annotations-e-type-annotations)
- [10. Melhorias em Coleções e Concorrência](#10-melhorias-em-coleções-e-concorrência)
- [11. Remoção do PermGen](#11-remoção-do-permgen-removal-of-permgen)
- [12. Melhorias em Segurança e Criptografia](#12-melhorias-em-segurança-e-criptografia)
- [13. Compact Profiles](#13-compact-profiles)
- [14. Melhorias no JavaFX](#14-melhorias-no-javafx)
- [15. Outras Menores](#15-outras-menores)


## 1. Expressões Lambda (Lambda Expressions) 🚀
As expressões lambda permitem tratar código como dados, facilitando a programação funcional. Elas são usadas para implementar interfaces funcionais (com um único método abstrato) de forma concisa.

**Exemplo:** Em vez de uma classe anônima para um comparator, você pode escrever `(a, b) -> a.compareTo(b)`. Isso reduz boilerplate e melhora a legibilidade, especialmente com coleções.

## 2. Referências a Métodos (Method References) 🔗
São uma forma ainda mais curta de expressões lambda, referenciando métodos existentes sem invocá-los.

**Exemplo:** `String::toUpperCase` em vez de `str -> str.toUpperCase()`. Útil para passar métodos como argumentos, tornando o código mais limpo e reutilizável.

## 3. Métodos Default em Interfaces (Default Methods) 🛡️
Permitem adicionar métodos implementados diretamente em interfaces, sem quebrar compatibilidade com classes existentes.

**Exemplo:** Em uma interface como `List`, você pode adicionar `default void sort() { ... }`. Isso facilita a evolução de APIs, como na atualização das coleções Java para suportar streams.

## 4. Métodos Estáticos em Interfaces (Static Methods in Interfaces) ⚙️
Semelhante aos default, mas estáticos. Permitem definir utilitários diretamente na interface.

**Exemplo:** `Comparator.naturalOrder()`. Ajuda a organizar código relacionado sem precisar de classes auxiliares.

## 5. API de Streams (Stream API) 🌊
Introduzida no pacote `java.util.stream`, permite processar coleções de forma funcional e paralela. Streams suportam operações como `map`, `filter`, `reduce` e `collect`.

**Exemplo:** `list.stream().filter(x -> x > 0).map(x -> x * 2).collect(Collectors.toList())`. É otimizada para multicore, melhorando desempenho em operações em massa.

## 6. Classe Optional (Optional Class) ❓
No pacote `java.util`, ajuda a evitar `NullPointerExceptions` representando valores que podem ser nulos.

**Exemplo:** `Optional.ofNullable(valor).orElse(default)`. Promove código mais seguro e expressivo, substituindo verificações manuais de null.

## 7. Nova API de Data e Hora (Date and Time API) ⏰
No pacote `java.time`, substitui as antigas classes como `Date` e `Calendar`, que eram problemáticas. Inclui classes como `LocalDate`, `LocalTime`, `ZonedDateTime` e `Duration`.

**Exemplo:** `LocalDate.now().plusDays(1)`. É imutável, thread-safe e suporta fusos horários e formatação avançada.

## 8. Motor JavaScript Nashorn (Nashorn JavaScript Engine) 📜
Substitui o antigo Rhino, permitindo executar código JavaScript diretamente no JVM via `jjs` ou APIs.

**Exemplo:** Usar `ScriptEngine` para rodar scripts dinâmicos. Útil para scripting e integração, como embedar JS em apps Java.

## 9. Anotações Repetíveis e em Tipos (Repeating Annotations e Type Annotations) 🔄
Permite aplicar a mesma anotação múltiplas vezes no mesmo elemento (repetíveis) e em qualquer uso de tipo (não só declarações).

**Exemplo:** `@NonNull` em parâmetros ou casts. Melhora verificações estáticas com ferramentas como Checkers Framework.

## 10. Melhorias em Coleções e Concorrência 🔄
- **Parallel Array Sorting:** Suporte a ordenação paralela de arrays via `Arrays.parallelSort()`. 📊
- **ConcurrentHashMap:** Adições para operações agregadas com streams e lambdas. 🗂️
- **ForkJoinPool:** Pool comum para tarefas paralelas. ⚡
- **StampedLock:** Novo lock otimizado para leitura/escrita. 🔒

Essas melhorias facilitam programação concorrente e paralela, aproveitando processadores multicore.

## 11. Remoção do PermGen (Removal of PermGen) 🗑️
O espaço de memória PermGen foi removido e substituído por Metaspace, que cresce dinamicamente. Reduz erros de `OutOfMemory` e melhora gerenciamento de classes.

## 12. Melhorias em Segurança e Criptografia 🔐
Inclui suporte a TLS 1.2 por default, algoritmos mais fortes (como AES/GCM), e checagem de revogação de certificados. Útil para apps web seguras.

## 13. Compact Profiles 📦
Subconjuntos do Java SE para dispositivos pequenos, permitindo deploy sem a plataforma inteira. Ideal para IoT ou embedded systems.

## 14. Melhorias no JavaFX 🎨
Adições como controles novos (`DatePicker`, `TreeTableView`), suporte a 3D, impressão e Hi-DPI. JavaFX tornou-se mais integrado, permitindo apps ricos em UI.

## 15. Outras Menores 🛠️
- **Inferência de Tipos Melhorada:** Facilita generics em chamadas de métodos.
- **Base64 Padrão:** Codificação/decodificação nativa via `Base64`.
- **Aritmética Não-Sinalizada:** Suporte a operações unsigned em inteiros.
- **JDBC 4.2:** Novas features para bancos de dados.


### Maximiliano R Pinto
