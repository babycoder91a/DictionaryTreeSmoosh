import React, { useState, useEffect } from 'react';

const sampleData = [
  'Apple',
  'Banana',
  'Orange',
  'Pineapple',
  'Mango',
  'Strawberry',
  'Blueberry',
  'Watermelon',
  'Kiwi',
  'Lemon',
  'Cherry',
  'Grapes',
  'Peach',
  'Pear',
];

const Bubble = ({ x, y, size, delay }) => {
  const style = {
    position: 'absolute',
    left: x,
    top: y,
    width: size,
    height: size,
    background: 'rgba(0, 255, 191, 0.3)',
    borderRadius: '50%',
    animation: `bubblePulse 4s ease-in-out ${delay}s infinite alternate`,
    filter: 'drop-shadow(0 0 6px rgba(0, 255, 191,0.7))',
    pointerEvents: 'none',
    zIndex: 0,
  };
  return <div style={style}></div>;
};

const App = () => {
  const [searchTerm, setSearchTerm] = useState('');
  const [filteredResults, setFilteredResults] = useState(sampleData);
  const [bubbles, setBubbles] = useState([]);

  // Filter results based on search term
  useEffect(() => {
    if (!searchTerm) {
      setFilteredResults(sampleData);
    } else {
      const filtered = sampleData.filter((item) =>
        item.toLowerCase().includes(searchTerm.toLowerCase())
      );
      setFilteredResults(filtered);
    }
  }, [searchTerm]);

  // Generate bubbles randomly on mount and on search term change
  useEffect(() => {
    const newBubbles = [];
    const bubbleCount = 12;
    for (let i = 0; i < bubbleCount; i++) {
      newBubbles.push({
        x: `${Math.random() * 90 + 5}%`,
        y: `${Math.random() * 80 + 10}%`,
        size: `${Math.random() * 60 + 30}px`,
        delay: Math.random() * 3,
      });
    }
    setBubbles(newBubbles);
  }, [searchTerm]);

  const containerStyle = {
    fontFamily: "'Poppins', sans-serif",
    height: '100vh',
    background: 'linear-gradient(135deg, #0072ff, #00c6ff)',
    color: '#e0f7fa',
    display: 'flex',
    flexDirection: 'column',
    alignItems: 'center',
    paddingTop: '4rem',
    position: 'relative',
    overflow: 'hidden',
  };

  const inputStyle = {
    padding: '0.75rem 1.5rem',
    borderRadius: '30px',
    border: 'none',
    width: '320px',
    fontSize: '1.2rem',
    outline: 'none',
    boxShadow: '0 0 18px rgba(0, 255, 191, 0.8)',
    backgroundColor: 'rgba(255, 255, 255, 0.1)',
    color: '#e0f7fa',
    marginBottom: '2rem',
    transition: 'box-shadow 0.3s ease',
  };

  const resultsStyle = {
    backgroundColor: 'rgba(255, 255, 255, 0.15)',
    borderRadius: '20px',
    width: '360px',
    padding: '1rem 1.5rem',
    maxHeight: '300px',
    overflowY: 'auto',
    boxShadow: '0 0 25px rgb(0 255 191 / 0.9)',
    zIndex: 1,
  };

  const resultItemStyle = {
    padding: '0.5rem 0',
    borderBottom: '1px solid rgba(224, 247, 250, 0.3)',
    cursor: 'pointer',
    fontSize: '1.1rem',
    transition: 'background-color 0.2s ease',
  };

  const titleStyle = {
    fontSize: '2.5rem',
    fontWeight: '700',
    marginBottom: '1rem',
    textShadow: '0 0 10px #00ffe3',
  };

  return (
    <div style={containerStyle}>
      <h1 style={titleStyle}>Blue-Green Bubble Search</h1>
      <input
        style={inputStyle}
        type="search"
        placeholder="Search fruits..."
        value={searchTerm}
        onChange={(e) => setSearchTerm(e.target.value)}
      />
      <div style={resultsStyle}>
        {filteredResults.length > 0 ? (
          filteredResults.map((item, index) => (
            <div
              key={index}
              style={resultItemStyle}
              onMouseEnter={(e) =>
                (e.currentTarget.style.backgroundColor = 'rgba(0, 255, 191, 0.3)')
              }
              onMouseLeave={(e) =>
                (e.currentTarget.style.backgroundColor = 'transparent')
              }
            >
              {item}
            </div>
          ))
        ) : (
          <p>No results found.</p>
        )}
      </div>

      {/* Bubbles */}
      {bubbles.map((bub, i) => (
        <Bubble key={i} x={bub.x} y={bub.y} size={bub.size} delay={bub.delay} />
      ))}

      <style>
        {`
          @keyframes bubblePulse {
            0% {
              transform: scale(1);
              opacity: 0.6;
            }
            100% {
              transform: scale(1.3);
              opacity: 0.3;
            }
          }
          ::-webkit-scrollbar {
            width: 8px;
          }
          ::-webkit-scrollbar-track {
            background: transparent;
          }
          ::-webkit-scrollbar-thumb {
            background-color: rgba(0, 255, 191, 0.5);
            border-radius: 20px;
          }
          `}
      </style>
    </div>
  );
};

export default App;

