[SVG Sequence - Looping](http://stackoverflow.com/questions/18319899/restart-entire-svg-animatetransform-sequence)

Looping Solution

	<svg>
	<circle id="test" fill="#ED1C24" cx="96.881" cy="91.953" r="26.485">
	  <animate id="first-ani" attributeName="fill" from="#ED1C24" to="#fff"
	    dur="2s" fill="freeze" begin="0s;second-ani.end+2s"/>  
	  <animate id="second-ani" attributeName="fill" from="" to="#ED1C24"
	    begin="first-ani.end" dur="2s" fill="freeze" />
	</circle>
	</svg>

`begin="first-ani.end"`

`begin=0s;second.end+2s`