<h1>Anti-patterns en schema para SEO local</h1>
<h2>Errores comunes y por qué evitarlos</h2>

<p>
Este documento recoge <strong>patrones incorrectos</strong> detectados de forma recurrente en proyectos de SEO local.
No son errores de sintaxis, sino <strong>errores de modelado de entidades</strong> que debilitan la relevancia,
la prominencia o la credibilidad.
</p>

<p>
El objetivo no es “marcar más”, sino <strong>marcar mejor</strong>.
</p>

<hr/>

<h2>1. Fingir proximidad con direcciones inexistentes</h2>

<h3>❌ Error</h3>
<pre><code class="language-json">
"address": {
  "@type": "PostalAddress",
  "addressLocality": "Girona"
}
</code></pre>

<p>
Usar <code>address</code>, <code>geo</code> o <code>hasMap</code> en ciudades donde
<strong>no existe sede física real</strong>.
</p>

<h3>Por qué es un problema</h3>
<ul>
  <li>Incoherencia entre schema, web y Google Business Profile</li>
  <li>Debilita señales de confianza</li>
  <li>Puede interpretarse como manipulación</li>
</ul>

<h3>✅ Qué hacer en su lugar</h3>
<ul>
  <li>Usar <code>serviceArea</code> en páginas de área de servicio</li>
  <li>Reservar <code>address</code> y <code>geo</code> solo para ubicaciones reales</li>
</ul>

<hr/>

<h2>2. Usar <code>sameAs</code> como lista de backlinks</h2>

<h3>❌ Error</h3>
<pre><code class="language-json">
"sameAs": [
  "https://medio.com/articulo-sobre-mi",
  "https://miweb.com/blog/post"
]
</code></pre>

<h3>Por qué es un problema</h3>
<p>
<code>sameAs</code> define <strong>identidad</strong>, no reputación.
</p>

<h3>✅ Qué hacer en su lugar</h3>
<ul>
  <li><code>sameAs</code> → perfiles oficiales y fichas estables</li>
  <li><code>subjectOf</code> → artículos, menciones y cobertura mediática</li>
</ul>

<hr/>

<h2>3. Autoreseñas o valoraciones inventadas</h2>

<h3>❌ Error</h3>
<p>
Añadir <code>review</code> o <code>aggregateRating</code> sin reseñas reales,
visibles o verificables.
</p>

<h3>Por qué es un problema</h3>
<ul>
  <li>Patrón clásico de <em>self-serving reviews</em></li>
  <li>Google lo ignora o lo invalida semánticamente</li>
</ul>

<h3>✅ Qué hacer en su lugar</h3>
<ul>
  <li>Usar <code>aggregateRating</code> solo con fuente pública real</li>
  <li>Indicar el origen (GBP, plataforma sectorial, etc.)</li>
  <li>Omitir reviews si no aportan señal real</li>
</ul>

<hr/>

<h2>4. Mezclar identidad del autor y rol editorial</h2>

<h3>❌ Error</h3>
<p>
Usar un único <code>Person</code> para identidad estable y autoría contextual
en distintos proyectos.
</p>

<h3>Por qué es un problema</h3>
<p>
Cuando un proyecto cae o cambia, <strong>arrastra la credibilidad del autor</strong>.
</p>

<h3>✅ Qué hacer en su lugar</h3>
<ul>
  <li><strong>Profile Person</strong> → identidad estable</li>
  <li><strong>Author schema</strong> → rol editorial contextual</li>
  <li>El autor <strong>no es</strong> la página de perfil</li>
</ul>

<hr/>

<h2>5. Keyword stuffing en <code>knowsAbout</code></h2>

<h3>❌ Error</h3>
<pre><code class="language-json">
"knowsAbout": [
  "SEO barato",
  "SEO Asturias",
  "Consultor SEO económico"
]
</code></pre>

<h3>Por qué es un problema</h3>
<ul>
  <li>No define conocimiento, sino intención comercial</li>
  <li>Pierde valor semántico</li>
</ul>

<h3>✅ Qué hacer en su lugar</h3>
<ul>
  <li>Usar conceptos reales</li>
  <li>Preferir entidades (Wikipedia / Wikidata)</li>
  <li>Delimitar especialización real</li>
</ul>

<hr/>

<h2>6. Usar <code>about</code> para apuntar a la propia marca</h2>

<h3>❌ Error</h3>
<pre><code class="language-json">
"about": {
  "@id": "https://midominio.com/#org"
}
</code></pre>

<h3>Por qué es un problema</h3>
<p>
<code>about</code> describe <strong>el tema del contenido</strong>, no el publicador.
</p>

<h3>✅ Qué hacer en su lugar</h3>
<ul>
  <li><code>about</code> → conceptos y temas</li>
  <li><code>publisher</code> / <code>provider</code> → organización</li>
</ul>

<hr/>

<h2>7. Duplicar el mismo schema en todas las páginas</h2>

<h3>❌ Error</h3>
<p>
Inyectar exactamente el mismo JSON-LD en home, servicios,
ubicaciones y contacto.
</p>

<h3>Por qué es un problema</h3>
<ul>
  <li>Elimina contexto</li>
  <li>Aplana el grafo</li>
  <li>Dificulta la interpretación</li>
</ul>

<h3>✅ Qué hacer en su lugar</h3>
<ul>
  <li>Reutilizar entidades por <code>@id</code></li>
  <li>Adaptar <code>WebPage</code>, <code>mainEntity</code> y <code>about</code></li>
</ul>

<hr/>

<h2>8. Inflar el grafo con propiedades irrelevantes</h2>

<h3>❌ Error</h3>
<p>
Añadir propiedades solo porque existen en schema.org.
</p>

<h3>Por qué es un problema</h3>
<ul>
  <li>Ruido semántico</li>
  <li>Señales débiles</li>
  <li>Mayor riesgo de errores</li>
</ul>

<h3>✅ Qué hacer en su lugar</h3>
<ul>
  <li>Incluir solo propiedades reales y verificables</li>
  <li>Coherentes con lo que ve el usuario</li>
</ul>

<hr/>

<h2>Principio final</h2>

<blockquote>
Schema no es para convencer a Google.<br/>
Es para <strong>no confundirlo</strong>.
</blockquote>

<p>
Si una propiedad no aclara <em>quién es la entidad</em>,
<em>dónde opera</em>, <em>de qué trata el contenido</em> o
<em>por qué es relevante</em>, probablemente sobra.
</p>
