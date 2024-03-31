Atributos de Thymeleaf con diferentes elementos HTML:

1. **th:text**: `<p>`, `<span>`, `<h1>`, `<div>`, etc.

   ```html
   <p th:text="${texto}"></p>
   <span th:text="${texto}"></span>
   <h1 th:text="${texto}"></h1>
   ```

2. **th:if / th:unless**: `<div>`, `<span>`, `<p>`, etc.

   ```html
   <div th:if="${condicion}">Contenido</div>
   <span th:unless="${condicion}">Contenido alternativo</span>
   ```

3. **th:each**: `<table>`, `<ul>`, `<ol>`, etc.

   ```html
   <table>
       <tr th:each="item : ${items}">
           <td th:text="${item}"></td>
       </tr>
   </table>
   ```

4. **th:href / th:src**: `<a>`, `<link>`, `<script>`, `<img>`, etc.

   ```html
   <a th:href="@{/ruta/dinamica}">Enlace</a>
   <img th:src="@{/ruta/dinamica/imagen.jpg}" alt="Imagen">
   ```

5. **th:switch / th:case**: `<div>`, `<span>`, etc.

   ```html
   <div th:switch="${variable}">
       <span th:case="1">Caso 1</span>
       <span th:case="2">Caso 2</span>
       <span th:case="*">Caso predeterminado</span>
   </div>
   ```

6. **th:class**: `<div>`, `<span>`, `<p>`, etc.

   ```html
   <div th:class="${condicion} ? 'clase-activa' : 'clase-inactiva'">Contenido</div>
   ```

7. **th:id**: Cualquier elemento HTML que necesite un ID.

   ```html
   <div th:id="${identificador}">Contenido</div>
   ```

8. **th:style**: Cualquier elemento HTML que necesite estilos CSS.

   ```html
   <div th:style="'background-color: ' + ${color} + ';'">Contenido</div>
   ```

9. **th:attr**: Cualquier elemento HTML que necesite atributos adicionales.

   ```html
   <input type="text" th:attr="data-id=${id}" />
   ```

10. **th:disabled**: `<input>`, `<button>`, etc.

    ```html
    <input type="submit" th:disabled="${condicion}" value="Enviar" />
    ```

11. **th:selected**: `<option>` dentro de un `<select>`.

    ```html
    <select>
        <option th:selected="${condicion}" value="1">Opción 1</option>
        <option th:selected="${!condicion}" value="2">Opción 2</option>
    </select>
    ```

12. **th:checked**: `<input type="checkbox">`, `<input type="radio">`, etc.

    ```html
    <input type="checkbox" th:checked="${condicion}" />
    ```

13. **th:value**: `<input>`, `<textarea>`, etc.

    ```html
    <input type="text" th:value="${valor}" />
    <textarea th:value="${texto}"></textarea>
    ```

14. **th:placeholder**: `<input>`, `<textarea>`, etc.

    ```html
    <input type="text" th:placeholder="Ingrese su nombre" />
    ```

15. **th:alt**: `<img>`, etc.

    ```html
    <img th:alt="${texto}" th:src="${url}" />
    ```

16. **th:title**: Cualquier elemento HTML que necesite un título.

    ```html
    <div th:title="${titulo}">Contenido</div>
    ```

17. **th:fragment**: Define fragmentos que pueden ser incluidos en otras partes de la plantilla.

    ```html
    <div th:fragment="miFragmento">
        Contenido del fragmento
    </div>
    ```

18. **th:remove**: Elimina elementos HTML basados en una condición.

    ```html
    <div th:remove="${condicion}"></div>
    ```

19. **th:object**: Define el objeto al que se refiere el contexto de la iteración.

    ```html
    <div th:each="item : ${items}" th:object="${item}">
        <span th:text="${item.nombre}"></span>
    </div>
    ```

20. **th:inline**: Permite la inclusión de scripts y fragmentos HTML inline.

    ```html
    <script th:inline="javascript">
        var data = [[${datos}]];
    </script>
    ```

Estos son solo ejemplos básicos de cómo usar los atributos de Thymeleaf con diferentes elementos HTML. Dependiendo de tu caso de uso específico, puedes necesitar ajustarlos para adaptarse a tus necesidades.
