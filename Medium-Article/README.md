Acesta este un aricol Mediu.

Contine:
HTML

<title>Titlul paginii</title>

<h1>Cea mai importanta rubrica (heading)</h1>
<h6>Cea mai pu?in importanta rubrica</h6>

<figure>
  <img src="http://nume-imagine.jpg" rel="text alternativ">
  <figcaption>Legenda pentru imagine</figcaption>
</figure>

<article>
  <p>Paragraf <a href="http://link-catre-ceva.com" title="Titlul paginii din link>cu link pe care se poate da clic</a></p>
  <p>Alt paragraf <strong>cu con?inut important</strong>.</p>
</article>

CSS:

 h1 {
      color:          rgba(0,0,0,.8);     // culoare, (red, green, blue, opacity (alpha))
      font-family:    serif;              // tip font
      font-size:      36px;               // marime font
      line-height:    1.58;               // înal?ime linie
      letter-spacing: -.003em;            // spa?iu între litere
      text-align:     center;             // aliniere text
    }

    img {
      height:         auto;               // înal?ime imagine
      width:          100%;               // la?ime imagine
    }

    figure {
      margin:         0;                  // margine
    }

    article {
      margin:         0 auto;             // centrat
    }

    a:hover {
                                          // starea când se trece cu mouse-ul
    }