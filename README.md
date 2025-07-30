
:root {
  --card-w: 120px;
  --card-h: 120px;
  --card-radius: 10px;
  --card-border: 3px;
  --card-blue: #0d6efd;
}

.cards-container {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
  padding: 20px;
}

.memory-card {
  position: relative;
  width: var(--card-w);
  height: var(--card-h);
  transform-style: preserve-3d;
  transition: transform 0.6s, box-shadow 0.3s;
  border-radius: var(--card-radius);
  cursor: pointer;
}

.memory-card:hover {
  box-shadow: 0 6px 20px rgba(13, 110, 253, 0.4);
  transform: scale(1.05);
}

.memory-card .back-face{
  position:absolute; inset:0;
  border-radius: var(--card-radius);
  border: var(--card-border) solid var(--card-blue); 
  background-color:#fff;   
  background-image:
    linear-gradient( 45deg, var(--card-blue) 25%, transparent 25%),
    linear-gradient(-45deg, var(--card-blue) 25%, transparent 25%),
    linear-gradient( 45deg, transparent 75%, var(--card-blue) 75%),
    linear-gradient(-45deg, transparent 75%, var(--card-blue) 75%);
  background-size: 20px 20px;   
  background-position: 0 0, 0 10px, 10px -10px, -10px 0px;
  
  backface-visibility:hidden;
}

.memory-card .front-face {
  position: absolute;
  inset: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 5rem;
  border-radius: var(--card-radius);
  backface-visibility: hidden;
  transform: rotateY(180deg);
}

.memory-card.tipo-1 .front-face {
  background: #ffffff;
  border: var(--card-border) solid var(--card-blue);
}


.memory-card.tipo-3 {
  --radius: 20px;
  --shadow: 0 8px 20px rgba(0, 0, 0, 0.25);
}
.memory-card.tipo-3 .back-face {
  background: #6f42c1;
}
.memory-card.tipo-3 .front-face {
  background: #fff;
}



/* Estado “girado” que puedes añadir con JS */
.memory-card.is-flipped {
  transform: rotateY(180deg);
}
