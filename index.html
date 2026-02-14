import React, { useState, useEffect } from 'react';
import { Calendar, MapPin, Clock, Heart, Users, ChevronDown, Search, Check } from 'lucide-react';

// Sample wedding data - customize this with your actual details
const WEDDING_DATA = {
  couple: {
    names: "Sarah & Michael",
    date: "June 15, 2026",
    hashtag: "#SarahAndMichael2026"
  },
  events: [
    {
      id: 'welcome',
      name: 'Welcome Drinks',
      date: 'Friday, June 14, 2026',
      time: '7:00 PM - 10:00 PM',
      location: 'The Garden Terrace',
      address: '123 Vineyard Lane, Napa Valley, CA',
      description: 'Join us for cocktails and appetizers the evening before the wedding.',
      invitationTypes: ['all', 'extended-family', 'wedding-party']
    },
    {
      id: 'ceremony',
      name: 'Wedding Ceremony',
      date: 'Saturday, June 15, 2026',
      time: '4:00 PM',
      location: 'Sunset Gardens',
      address: '456 Estate Road, Napa Valley, CA',
      description: 'Our ceremony will take place in the beautiful garden overlooking the valley.',
      invitationTypes: ['all', 'ceremony-only', 'extended-family', 'wedding-party']
    },
    {
      id: 'reception',
      name: 'Reception & Dinner',
      date: 'Saturday, June 15, 2026',
      time: '6:00 PM - 11:00 PM',
      location: 'The Grand Ballroom',
      address: '456 Estate Road, Napa Valley, CA',
      description: 'Dinner, dancing, and celebration under the stars.',
      invitationTypes: ['all', 'extended-family', 'wedding-party']
    },
    {
      id: 'brunch',
      name: 'Farewell Brunch',
      date: 'Sunday, June 16, 2026',
      time: '11:00 AM - 1:00 PM',
      location: 'The Estate Courtyard',
      address: '456 Estate Road, Napa Valley, CA',
      description: 'A casual brunch to say goodbye before we all head home.',
      invitationTypes: ['wedding-party', 'extended-family']
    }
  ],
  // Sample guest list - in production, this would be much more comprehensive
  guestList: [
    { name: 'John Smith', email: 'john@example.com', invitationType: 'all', plusOne: true },
    { name: 'Emily Johnson', email: 'emily@example.com', invitationType: 'all', plusOne: false },
    { name: 'Robert Williams', email: 'robert@example.com', invitationType: 'ceremony-only', plusOne: true },
    { name: 'Jessica Brown', email: 'jessica@example.com', invitationType: 'extended-family', plusOne: true },
    { name: 'David Miller', email: 'david@example.com', invitationType: 'wedding-party', plusOne: true },
  ]
};

const WeddingWebsite = () => {
  const [currentView, setCurrentView] = useState('home');
  const [selectedGuest, setSelectedGuest] = useState(null);
  const [searchQuery, setSearchQuery] = useState('');
  const [rsvpData, setRsvpData] = useState({
    attending: null,
    guestName: '',
    plusOneName: '',
    plusOneAttending: null,
    dietaryRestrictions: '',
    songRequest: ''
  });
  const [rsvpSubmitted, setRsvpSubmitted] = useState(false);
  const [allRsvps, setAllRsvps] = useState([]);
  const [loading, setLoading] = useState(false);

  // Load RSVPs on mount
  useEffect(() => {
    loadRsvps();
  }, []);

  const loadRsvps = async () => {
    try {
      const keys = await window.storage.list('rsvp:', true);
      if (keys && keys.keys) {
        const rsvps = await Promise.all(
          keys.keys.map(async (key) => {
            try {
              const result = await window.storage.get(key, true);
              return result ? JSON.parse(result.value) : null;
            } catch {
              return null;
            }
          })
        );
        setAllRsvps(rsvps.filter(r => r !== null));
      }
    } catch (error) {
      console.log('Could not load RSVPs:', error);
    }
  };

  const handleGuestSearch = (query) => {
    setSearchQuery(query);
    if (query.length < 2) {
      setSelectedGuest(null);
      return;
    }

    const found = WEDDING_DATA.guestList.find(guest =>
      guest.name.toLowerCase().includes(query.toLowerCase())
    );
    
    if (found) {
      setSelectedGuest(found);
      setRsvpData(prev => ({ ...prev, guestName: found.name }));
    } else {
      setSelectedGuest(null);
    }
  };

  const handleRsvpSubmit = async () => {
    if (!selectedGuest || rsvpData.attending === null) return;

    setLoading(true);
    const submission = {
      ...rsvpData,
      email: selectedGuest.email,
      invitationType: selectedGuest.invitationType,
      timestamp: new Date().toISOString()
    };

    try {
      await window.storage.set(`rsvp:${selectedGuest.email}`, JSON.stringify(submission), true);
      setRsvpSubmitted(true);
      loadRsvps();
    } catch (error) {
      alert('There was an error submitting your RSVP. Please try again.');
    } finally {
      setLoading(false);
    }
  };

  const getGuestEvents = (invitationType) => {
    return WEDDING_DATA.events.filter(event =>
      event.invitationTypes.includes(invitationType) || event.invitationTypes.includes('all')
    );
  };

  const filteredGuests = WEDDING_DATA.guestList.filter(guest =>
    guest.name.toLowerCase().includes(searchQuery.toLowerCase())
  );

  return (
    <div style={{
      minHeight: '100vh',
      background: 'linear-gradient(135deg, #fdfbf7 0%, #f8f4ed 100%)',
      fontFamily: "'Cormorant Garamond', serif"
    }}>
      {/* Header */}
      <header style={{
        background: 'linear-gradient(to bottom, rgba(255,255,255,0.95), rgba(253,251,247,0.9))',
        borderBottom: '1px solid rgba(139,116,95,0.15)',
        position: 'sticky',
        top: 0,
        zIndex: 1000,
        backdropFilter: 'blur(10px)'
      }}>
        <div style={{
          maxWidth: '1200px',
          margin: '0 auto',
          padding: '1.5rem 2rem',
          display: 'flex',
          justifyContent: 'space-between',
          alignItems: 'center'
        }}>
          <div style={{
            fontSize: '1.75rem',
            fontWeight: 500,
            color: '#2c3e50',
            letterSpacing: '0.05em'
          }}>
            {WEDDING_DATA.couple.names}
          </div>
          <nav style={{ display: 'flex', gap: '2.5rem' }}>
            {['home', 'schedule', 'rsvp', 'admin'].map(view => (
              <button
                key={view}
                onClick={() => setCurrentView(view)}
                style={{
                  background: 'none',
                  border: 'none',
                  color: currentView === view ? '#8b745f' : '#5a5a5a',
                  fontSize: '1.1rem',
                  cursor: 'pointer',
                  fontFamily: "'Cormorant Garamond', serif",
                  fontWeight: currentView === view ? 600 : 400,
                  textTransform: 'uppercase',
                  letterSpacing: '0.1em',
                  transition: 'all 0.3s ease',
                  position: 'relative',
                  padding: '0.5rem 0'
                }}
              >
                {view}
                {currentView === view && (
                  <div style={{
                    position: 'absolute',
                    bottom: 0,
                    left: 0,
                    right: 0,
                    height: '2px',
                    background: '#8b745f'
                  }} />
                )}
              </button>
            ))}
          </nav>
        </div>
      </header>

      {/* Main Content */}
      <main style={{ maxWidth: '1200px', margin: '0 auto', padding: '4rem 2rem' }}>
        
        {/* HOME VIEW */}
        {currentView === 'home' && (
          <div style={{ textAlign: 'center', animation: 'fadeIn 0.6s ease' }}>
            <div style={{
              display: 'inline-block',
              padding: '1rem 2rem',
              border: '1px solid rgba(139,116,95,0.3)',
              borderRadius: '50px',
              marginBottom: '2rem',
              fontSize: '0.95rem',
              color: '#8b745f',
              letterSpacing: '0.15em',
              textTransform: 'uppercase'
            }}>
              Save the Date
            </div>
            
            <h1 style={{
              fontSize: '6rem',
              fontWeight: 400,
              margin: '2rem 0',
              color: '#2c3e50',
              lineHeight: 1.2
            }}>
              {WEDDING_DATA.couple.names}
            </h1>
            
            <div style={{
              fontSize: '2rem',
              color: '#8b745f',
              margin: '2rem 0',
              fontStyle: 'italic'
            }}>
              {WEDDING_DATA.couple.date}
            </div>

            <div style={{
              maxWidth: '600px',
              margin: '3rem auto',
              fontSize: '1.3rem',
              lineHeight: 1.8,
              color: '#5a5a5a'
            }}>
              Join us as we celebrate our love and commitment to each other.
              We can't wait to share this special day with you.
            </div>

            <div style={{
              display: 'flex',
              justifyContent: 'center',
              gap: '2rem',
              marginTop: '4rem'
            }}>
              <button
                onClick={() => setCurrentView('rsvp')}
                style={{
                  padding: '1rem 3rem',
                  background: '#8b745f',
                  color: 'white',
                  border: 'none',
                  borderRadius: '50px',
                  fontSize: '1.1rem',
                  cursor: 'pointer',
                  fontFamily: "'Cormorant Garamond', serif",
                  letterSpacing: '0.1em',
                  textTransform: 'uppercase',
                  transition: 'all 0.3s ease',
                  boxShadow: '0 4px 15px rgba(139,116,95,0.2)'
                }}
                onMouseEnter={(e) => {
                  e.target.style.transform = 'translateY(-2px)';
                  e.target.style.boxShadow = '0 6px 20px rgba(139,116,95,0.3)';
                }}
                onMouseLeave={(e) => {
                  e.target.style.transform = 'translateY(0)';
                  e.target.style.boxShadow = '0 4px 15px rgba(139,116,95,0.2)';
                }}
              >
                RSVP Now
              </button>
              
              <button
                onClick={() => setCurrentView('schedule')}
                style={{
                  padding: '1rem 3rem',
                  background: 'transparent',
                  color: '#8b745f',
                  border: '2px solid #8b745f',
                  borderRadius: '50px',
                  fontSize: '1.1rem',
                  cursor: 'pointer',
                  fontFamily: "'Cormorant Garamond', serif",
                  letterSpacing: '0.1em',
                  textTransform: 'uppercase',
                  transition: 'all 0.3s ease'
                }}
                onMouseEnter={(e) => {
                  e.target.style.background = '#8b745f';
                  e.target.style.color = 'white';
                }}
                onMouseLeave={(e) => {
                  e.target.style.background = 'transparent';
                  e.target.style.color = '#8b745f';
                }}
              >
                View Schedule
              </button>
            </div>

            <div style={{
              marginTop: '6rem',
              fontSize: '1.5rem',
              color: '#8b745f',
              fontStyle: 'italic'
            }}>
              {WEDDING_DATA.couple.hashtag}
            </div>
          </div>
        )}

        {/* SCHEDULE VIEW */}
        {currentView === 'schedule' && (
          <div style={{ animation: 'fadeIn 0.6s ease' }}>
            <h2 style={{
              fontSize: '4rem',
              fontWeight: 400,
              textAlign: 'center',
              marginBottom: '1rem',
              color: '#2c3e50'
            }}>
              Event Schedule
            </h2>
            
            <p style={{
              textAlign: 'center',
              color: '#8b745f',
              fontSize: '1.2rem',
              marginBottom: '4rem',
              fontStyle: 'italic'
            }}>
              Enter your name to see your personalized schedule
            </p>

            {/* Guest Search */}
            <div style={{
              maxWidth: '500px',
              margin: '0 auto 4rem',
              position: 'relative'
            }}>
              <div style={{ position: 'relative' }}>
                <Search size={20} style={{
                  position: 'absolute',
                  left: '1.5rem',
                  top: '50%',
                  transform: 'translateY(-50%)',
                  color: '#8b745f'
                }} />
                <input
                  type="text"
                  placeholder="Search for your name..."
                  value={searchQuery}
                  onChange={(e) => handleGuestSearch(e.target.value)}
                  style={{
                    width: '100%',
                    padding: '1rem 1rem 1rem 3.5rem',
                    border: '2px solid rgba(139,116,95,0.3)',
                    borderRadius: '50px',
                    fontSize: '1.1rem',
                    fontFamily: "'Cormorant Garamond', serif",
                    outline: 'none',
                    transition: 'all 0.3s ease'
                  }}
                  onFocus={(e) => e.target.style.borderColor = '#8b745f'}
                  onBlur={(e) => e.target.style.borderColor = 'rgba(139,116,95,0.3)'}
                />
              </div>

              {searchQuery && filteredGuests.length > 0 && !selectedGuest && (
                <div style={{
                  position: 'absolute',
                  top: '100%',
                  left: 0,
                  right: 0,
                  background: 'white',
                  border: '2px solid rgba(139,116,95,0.3)',
                  borderRadius: '20px',
                  marginTop: '0.5rem',
                  maxHeight: '200px',
                  overflowY: 'auto',
                  boxShadow: '0 4px 20px rgba(0,0,0,0.1)',
                  zIndex: 10
                }}>
                  {filteredGuests.map(guest => (
                    <div
                      key={guest.email}
                      onClick={() => {
                        setSelectedGuest(guest);
                        setSearchQuery(guest.name);
                      }}
                      style={{
                        padding: '1rem 1.5rem',
                        cursor: 'pointer',
                        borderBottom: '1px solid rgba(139,116,95,0.1)',
                        transition: 'background 0.2s ease'
                      }}
                      onMouseEnter={(e) => e.target.style.background = '#fdfbf7'}
                      onMouseLeave={(e) => e.target.style.background = 'white'}
                    >
                      {guest.name}
                    </div>
                  ))}
                </div>
              )}
            </div>

            {selectedGuest && (
              <div style={{
                background: 'rgba(139,116,95,0.05)',
                border: '2px solid rgba(139,116,95,0.2)',
                borderRadius: '20px',
                padding: '2rem',
                marginBottom: '3rem',
                textAlign: 'center'
              }}>
                <div style={{ fontSize: '1.5rem', color: '#2c3e50', marginBottom: '0.5rem' }}>
                  Welcome, {selectedGuest.name}!
                </div>
                <div style={{ color: '#8b745f', fontSize: '1.1rem' }}>
                  Here are the events you're invited to attend
                </div>
              </div>
            )}

            {/* Events */}
            <div style={{
              display: 'grid',
              gap: '2rem',
              maxWidth: '900px',
              margin: '0 auto'
            }}>
              {(selectedGuest ? getGuestEvents(selectedGuest.invitationType) : WEDDING_DATA.events).map((event, index) => (
                <div
                  key={event.id}
                  style={{
                    background: 'white',
                    borderRadius: '20px',
                    padding: '2.5rem',
                    boxShadow: '0 4px 20px rgba(0,0,0,0.08)',
                    border: '1px solid rgba(139,116,95,0.1)',
                    animation: `slideUp 0.6s ease ${index * 0.1}s backwards`
                  }}
                >
                  <div style={{
                    display: 'flex',
                    justifyContent: 'space-between',
                    alignItems: 'flex-start',
                    marginBottom: '1.5rem'
                  }}>
                    <h3 style={{
                      fontSize: '2rem',
                      fontWeight: 500,
                      color: '#2c3e50',
                      margin: 0
                    }}>
                      {event.name}
                    </h3>
                    <div style={{
                      background: 'rgba(139,116,95,0.1)',
                      padding: '0.5rem 1rem',
                      borderRadius: '20px',
                      fontSize: '0.9rem',
                      color: '#8b745f',
                      whiteSpace: 'nowrap'
                    }}>
                      {event.date.split(',')[0]}
                    </div>
                  </div>

                  <div style={{ display: 'flex', flexDirection: 'column', gap: '1rem' }}>
                    <div style={{ display: 'flex', alignItems: 'center', gap: '1rem' }}>
                      <Calendar size={20} color="#8b745f" />
                      <span style={{ color: '#5a5a5a', fontSize: '1.1rem' }}>{event.date}</span>
                    </div>
                    <div style={{ display: 'flex', alignItems: 'center', gap: '1rem' }}>
                      <Clock size={20} color="#8b745f" />
                      <span style={{ color: '#5a5a5a', fontSize: '1.1rem' }}>{event.time}</span>
                    </div>
                    <div style={{ display: 'flex', alignItems: 'center', gap: '1rem' }}>
                      <MapPin size={20} color="#8b745f" />
                      <div>
                        <div style={{ color: '#5a5a5a', fontSize: '1.1rem', fontWeight: 500 }}>
                          {event.location}
                        </div>
                        <div style={{ color: '#999', fontSize: '0.95rem', marginTop: '0.25rem' }}>
                          {event.address}
                        </div>
                      </div>
                    </div>
                  </div>

                  <p style={{
                    marginTop: '1.5rem',
                    color: '#5a5a5a',
                    fontSize: '1.1rem',
                    lineHeight: 1.6,
                    fontStyle: 'italic'
                  }}>
                    {event.description}
                  </p>
                </div>
              ))}
            </div>
          </div>
        )}

        {/* RSVP VIEW */}
        {currentView === 'rsvp' && (
          <div style={{ animation: 'fadeIn 0.6s ease' }}>
            <h2 style={{
              fontSize: '4rem',
              fontWeight: 400,
              textAlign: 'center',
              marginBottom: '1rem',
              color: '#2c3e50'
            }}>
              RSVP
            </h2>
            
            <p style={{
              textAlign: 'center',
              color: '#8b745f',
              fontSize: '1.2rem',
              marginBottom: '4rem',
              fontStyle: 'italic'
            }}>
              We hope you can join us for our special day
            </p>

            {!rsvpSubmitted ? (
              <div style={{
                maxWidth: '600px',
                margin: '0 auto',
                background: 'white',
                borderRadius: '20px',
                padding: '3rem',
                boxShadow: '0 4px 30px rgba(0,0,0,0.1)',
                border: '1px solid rgba(139,116,95,0.1)'
              }}>
                {/* Guest Search */}
                <div style={{ marginBottom: '2rem' }}>
                  <label style={{
                    display: 'block',
                    marginBottom: '0.75rem',
                    color: '#2c3e50',
                    fontSize: '1.1rem',
                    fontWeight: 500
                  }}>
                    Find Your Invitation
                  </label>
                  <div style={{ position: 'relative' }}>
                    <Search size={20} style={{
                      position: 'absolute',
                      left: '1rem',
                      top: '50%',
                      transform: 'translateY(-50%)',
                      color: '#8b745f'
                    }} />
                    <input
                      type="text"
                      placeholder="Enter your name"
                      value={searchQuery}
                      onChange={(e) => handleGuestSearch(e.target.value)}
                      style={{
                        width: '100%',
                        padding: '0.875rem 1rem 0.875rem 3rem',
                        border: '2px solid rgba(139,116,95,0.3)',
                        borderRadius: '10px',
                        fontSize: '1rem',
                        fontFamily: "'Cormorant Garamond', serif",
                        outline: 'none'
                      }}
                    />
                  </div>
                  
                  {searchQuery && filteredGuests.length > 0 && !selectedGuest && (
                    <div style={{
                      marginTop: '0.5rem',
                      background: '#fdfbf7',
                      border: '1px solid rgba(139,116,95,0.2)',
                      borderRadius: '10px',
                      maxHeight: '150px',
                      overflowY: 'auto'
                    }}>
                      {filteredGuests.map(guest => (
                        <div
                          key={guest.email}
                          onClick={() => {
                            setSelectedGuest(guest);
                            setSearchQuery(guest.name);
                          }}
                          style={{
                            padding: '0.75rem 1rem',
                            cursor: 'pointer',
                            borderBottom: '1px solid rgba(139,116,95,0.1)'
                          }}
                          onMouseEnter={(e) => e.target.style.background = 'white'}
                          onMouseLeave={(e) => e.target.style.background = 'transparent'}
                        >
                          {guest.name}
                        </div>
                      ))}
                    </div>
                  )}
                  
                  {selectedGuest && (
                    <div style={{
                      marginTop: '1rem',
                      padding: '1rem',
                      background: 'rgba(139,116,95,0.05)',
                      borderRadius: '10px',
                      display: 'flex',
                      alignItems: 'center',
                      gap: '0.5rem'
                    }}>
                      <Check size={18} color="#8b745f" />
                      <span style={{ color: '#8b745f' }}>Invitation found for {selectedGuest.name}</span>
                    </div>
                  )}
                </div>

                {selectedGuest && (
                  <>
                    {/* Attendance */}
                    <div style={{ marginBottom: '2rem' }}>
                      <label style={{
                        display: 'block',
                        marginBottom: '0.75rem',
                        color: '#2c3e50',
                        fontSize: '1.1rem',
                        fontWeight: 500
                      }}>
                        Will you be attending?
                      </label>
                      <div style={{ display: 'flex', gap: '1rem' }}>
                        {[
                          { value: true, label: 'Joyfully Accept', icon: '✓' },
                          { value: false, label: 'Regretfully Decline', icon: '✗' }
                        ].map(option => (
                          <button
                            key={option.label}
                            onClick={() => setRsvpData({ ...rsvpData, attending: option.value })}
                            style={{
                              flex: 1,
                              padding: '1rem',
                              background: rsvpData.attending === option.value ? '#8b745f' : 'transparent',
                              color: rsvpData.attending === option.value ? 'white' : '#5a5a5a',
                              border: `2px solid ${rsvpData.attending === option.value ? '#8b745f' : 'rgba(139,116,95,0.3)'}`,
                              borderRadius: '10px',
                              fontSize: '1rem',
                              cursor: 'pointer',
                              fontFamily: "'Cormorant Garamond', serif",
                              transition: 'all 0.3s ease'
                            }}
                          >
                            <div style={{ fontSize: '1.5rem', marginBottom: '0.25rem' }}>{option.icon}</div>
                            {option.label}
                          </button>
                        ))}
                      </div>
                    </div>

                    {/* Plus One */}
                    {selectedGuest.plusOne && rsvpData.attending && (
                      <>
                        <div style={{ marginBottom: '2rem' }}>
                          <label style={{
                            display: 'block',
                            marginBottom: '0.75rem',
                            color: '#2c3e50',
                            fontSize: '1.1rem',
                            fontWeight: 500
                          }}>
                            Guest Name (if bringing a plus one)
                          </label>
                          <input
                            type="text"
                            placeholder="Enter guest name"
                            value={rsvpData.plusOneName}
                            onChange={(e) => setRsvpData({ ...rsvpData, plusOneName: e.target.value })}
                            style={{
                              width: '100%',
                              padding: '0.875rem 1rem',
                              border: '2px solid rgba(139,116,95,0.3)',
                              borderRadius: '10px',
                              fontSize: '1rem',
                              fontFamily: "'Cormorant Garamond', serif",
                              outline: 'none'
                            }}
                          />
                        </div>

                        {rsvpData.plusOneName && (
                          <div style={{ marginBottom: '2rem' }}>
                            <label style={{
                              display: 'block',
                              marginBottom: '0.75rem',
                              color: '#2c3e50',
                              fontSize: '1.1rem',
                              fontWeight: 500
                            }}>
                              Will {rsvpData.plusOneName} be attending?
                            </label>
                            <div style={{ display: 'flex', gap: '1rem' }}>
                              {[
                                { value: true, label: 'Yes' },
                                { value: false, label: 'No' }
                              ].map(option => (
                                <button
                                  key={option.label}
                                  onClick={() => setRsvpData({ ...rsvpData, plusOneAttending: option.value })}
                                  style={{
                                    flex: 1,
                                    padding: '0.875rem',
                                    background: rsvpData.plusOneAttending === option.value ? '#8b745f' : 'transparent',
                                    color: rsvpData.plusOneAttending === option.value ? 'white' : '#5a5a5a',
                                    border: `2px solid ${rsvpData.plusOneAttending === option.value ? '#8b745f' : 'rgba(139,116,95,0.3)'}`,
                                    borderRadius: '10px',
                                    fontSize: '1rem',
                                    cursor: 'pointer',
                                    fontFamily: "'Cormorant Garamond', serif",
                                    transition: 'all 0.3s ease'
                                  }}
                                >
                                  {option.label}
                                </button>
                              ))}
                            </div>
                          </div>
                        )}
                      </>
                    )}

                    {rsvpData.attending && (
                      <>
                        {/* Dietary Restrictions */}
                        <div style={{ marginBottom: '2rem' }}>
                          <label style={{
                            display: 'block',
                            marginBottom: '0.75rem',
                            color: '#2c3e50',
                            fontSize: '1.1rem',
                            fontWeight: 500
                          }}>
                            Dietary Restrictions or Allergies
                          </label>
                          <textarea
                            placeholder="Let us know about any dietary needs..."
                            value={rsvpData.dietaryRestrictions}
                            onChange={(e) => setRsvpData({ ...rsvpData, dietaryRestrictions: e.target.value })}
                            style={{
                              width: '100%',
                              padding: '0.875rem 1rem',
                              border: '2px solid rgba(139,116,95,0.3)',
                              borderRadius: '10px',
                              fontSize: '1rem',
                              fontFamily: "'Cormorant Garamond', serif",
                              outline: 'none',
                              resize: 'vertical',
                              minHeight: '80px'
                            }}
                          />
                        </div>

                        {/* Song Request */}
                        <div style={{ marginBottom: '2rem' }}>
                          <label style={{
                            display: 'block',
                            marginBottom: '0.75rem',
                            color: '#2c3e50',
                            fontSize: '1.1rem',
                            fontWeight: 500
                          }}>
                            Song Request
                          </label>
                          <input
                            type="text"
                            placeholder="What song will get you on the dance floor?"
                            value={rsvpData.songRequest}
                            onChange={(e) => setRsvpData({ ...rsvpData, songRequest: e.target.value })}
                            style={{
                              width: '100%',
                              padding: '0.875rem 1rem',
                              border: '2px solid rgba(139,116,95,0.3)',
                              borderRadius: '10px',
                              fontSize: '1rem',
                              fontFamily: "'Cormorant Garamond', serif",
                              outline: 'none'
                            }}
                          />
                        </div>
                      </>
                    )}

                    {/* Submit Button */}
                    <button
                      onClick={handleRsvpSubmit}
                      disabled={rsvpData.attending === null || loading}
                      style={{
                        width: '100%',
                        padding: '1rem',
                        background: rsvpData.attending === null ? '#ccc' : '#8b745f',
                        color: 'white',
                        border: 'none',
                        borderRadius: '10px',
                        fontSize: '1.2rem',
                        cursor: rsvpData.attending === null ? 'not-allowed' : 'pointer',
                        fontFamily: "'Cormorant Garamond', serif',
                        letterSpacing: '0.1em',
                        textTransform: 'uppercase',
                        transition: 'all 0.3s ease',
                        opacity: loading ? 0.7 : 1
                      }}
                    >
                      {loading ? 'Submitting...' : 'Submit RSVP'}
                    </button>
                  </>
                )}
              </div>
            ) : (
              <div style={{
                maxWidth: '600px',
                margin: '0 auto',
                background: 'white',
                borderRadius: '20px',
                padding: '4rem 3rem',
                boxShadow: '0 4px 30px rgba(0,0,0,0.1)',
                textAlign: 'center'
              }}>
                <Heart size={60} color="#8b745f" style={{ marginBottom: '2rem' }} />
                <h3 style={{
                  fontSize: '2.5rem',
                  fontWeight: 400,
                  color: '#2c3e50',
                  marginBottom: '1rem'
                }}>
                  Thank You!
                </h3>
                <p style={{
                  fontSize: '1.2rem',
                  color: '#5a5a5a',
                  lineHeight: 1.6,
                  marginBottom: '2rem'
                }}>
                  Your RSVP has been received. We {rsvpData.attending ? "can't wait to celebrate with you" : "understand and will miss you on our special day"}.
                </p>
                <button
                  onClick={() => {
                    setRsvpSubmitted(false);
                    setSelectedGuest(null);
                    setSearchQuery('');
                    setRsvpData({
                      attending: null,
                      guestName: '',
                      plusOneName: '',
                      plusOneAttending: null,
                      dietaryRestrictions: '',
                      songRequest: ''
                    });
                  }}
                  style={{
                    padding: '0.875rem 2rem',
                    background: 'transparent',
                    color: '#8b745f',
                    border: '2px solid #8b745f',
                    borderRadius: '50px',
                    fontSize: '1rem',
                    cursor: 'pointer',
                    fontFamily: "'Cormorant Garamond', serif",
                    letterSpacing: '0.1em',
                    textTransform: 'uppercase'
                  }}
                >
                  Submit Another RSVP
                </button>
              </div>
            )}
          </div>
        )}

        {/* ADMIN VIEW */}
        {currentView === 'admin' && (
          <div style={{ animation: 'fadeIn 0.6s ease' }}>
            <h2 style={{
              fontSize: '4rem',
              fontWeight: 400,
              textAlign: 'center',
              marginBottom: '1rem',
              color: '#2c3e50'
            }}>
              RSVP Management
            </h2>
            
            <p style={{
              textAlign: 'center',
              color: '#8b745f',
              fontSize: '1.2rem',
              marginBottom: '2rem',
              fontStyle: 'italic'
            }}>
              Track all your guest responses
            </p>

            <div style={{
              display: 'flex',
              gap: '2rem',
              justifyContent: 'center',
              marginBottom: '3rem'
            }}>
              <div style={{
                background: 'rgba(139,116,95,0.1)',
                padding: '1.5rem 2.5rem',
                borderRadius: '15px',
                textAlign: 'center'
              }}>
                <div style={{ fontSize: '3rem', fontWeight: 500, color: '#8b745f' }}>
                  {allRsvps.filter(r => r.attending).length}
                </div>
                <div style={{ fontSize: '1.1rem', color: '#5a5a5a', marginTop: '0.5rem' }}>
                  Attending
                </div>
              </div>
              
              <div style={{
                background: 'rgba(139,116,95,0.1)',
                padding: '1.5rem 2.5rem',
                borderRadius: '15px',
                textAlign: 'center'
              }}>
                <div style={{ fontSize: '3rem', fontWeight: 500, color: '#5a5a5a' }}>
                  {allRsvps.filter(r => !r.attending).length}
                </div>
                <div style={{ fontSize: '1.1rem', color: '#5a5a5a', marginTop: '0.5rem' }}>
                  Not Attending
                </div>
              </div>
              
              <div style={{
                background: 'rgba(139,116,95,0.1)',
                padding: '1.5rem 2.5rem',
                borderRadius: '15px',
                textAlign: 'center'
              }}>
                <div style={{ fontSize: '3rem', fontWeight: 500, color: '#2c3e50' }}>
                  {allRsvps.length}
                </div>
                <div style={{ fontSize: '1.1rem', color: '#5a5a5a', marginTop: '0.5rem' }}>
                  Total Responses
                </div>
              </div>
            </div>

            {allRsvps.length > 0 ? (
              <div style={{
                background: 'white',
                borderRadius: '20px',
                padding: '2rem',
                boxShadow: '0 4px 20px rgba(0,0,0,0.08)',
                overflowX: 'auto'
              }}>
                <table style={{
                  width: '100%',
                  borderCollapse: 'separate',
                  borderSpacing: 0
                }}>
                  <thead>
                    <tr style={{ borderBottom: '2px solid rgba(139,116,95,0.2)' }}>
                      <th style={{ padding: '1rem', textAlign: 'left', color: '#2c3e50', fontSize: '1.1rem' }}>Guest</th>
                      <th style={{ padding: '1rem', textAlign: 'left', color: '#2c3e50', fontSize: '1.1rem' }}>Status</th>
                      <th style={{ padding: '1rem', textAlign: 'left', color: '#2c3e50', fontSize: '1.1rem' }}>Plus One</th>
                      <th style={{ padding: '1rem', textAlign: 'left', color: '#2c3e50', fontSize: '1.1rem' }}>Dietary</th>
                      <th style={{ padding: '1rem', textAlign: 'left', color: '#2c3e50', fontSize: '1.1rem' }}>Song</th>
                    </tr>
                  </thead>
                  <tbody>
                    {allRsvps.map((rsvp, index) => (
                      <tr
                        key={index}
                        style={{
                          borderBottom: '1px solid rgba(139,116,95,0.1)',
                          transition: 'background 0.2s ease'
                        }}
                        onMouseEnter={(e) => e.currentTarget.style.background = '#fdfbf7'}
                        onMouseLeave={(e) => e.currentTarget.style.background = 'transparent'}
                      >
                        <td style={{ padding: '1rem', color: '#2c3e50' }}>{rsvp.guestName}</td>
                        <td style={{ padding: '1rem' }}>
                          <span style={{
                            padding: '0.25rem 0.75rem',
                            borderRadius: '20px',
                            fontSize: '0.9rem',
                            background: rsvp.attending ? 'rgba(139,116,95,0.2)' : 'rgba(90,90,90,0.1)',
                            color: rsvp.attending ? '#8b745f' : '#5a5a5a'
                          }}>
                            {rsvp.attending ? 'Attending' : 'Not Attending'}
                          </span>
                        </td>
                        <td style={{ padding: '1rem', color: '#5a5a5a' }}>
                          {rsvp.plusOneName || '—'}
                          {rsvp.plusOneName && rsvp.plusOneAttending !== null && (
                            <span style={{ marginLeft: '0.5rem', fontSize: '0.9rem' }}>
                              ({rsvp.plusOneAttending ? '✓' : '✗'})
                            </span>
                          )}
                        </td>
                        <td style={{ padding: '1rem', color: '#5a5a5a' }}>
                          {rsvp.dietaryRestrictions || '—'}
                        </td>
                        <td style={{ padding: '1rem', color: '#5a5a5a' }}>
                          {rsvp.songRequest || '—'}
                        </td>
                      </tr>
                    ))}
                  </tbody>
                </table>
              </div>
            ) : (
              <div style={{
                textAlign: 'center',
                padding: '4rem',
                color: '#5a5a5a',
                fontSize: '1.2rem'
              }}>
                No RSVPs received yet
              </div>
            )}
          </div>
        )}
      </main>

      {/* Animations */}
      <style>{`
        @import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;1,400&display=swap');
        
        @keyframes fadeIn {
          from {
            opacity: 0;
            transform: translateY(20px);
          }
          to {
            opacity: 1;
            transform: translateY(0);
          }
        }
        
        @keyframes slideUp {
          from {
            opacity: 0;
            transform: translateY(30px);
          }
          to {
            opacity: 1;
            transform: translateY(0);
          }
        }
      `}</style>
    </div>
  );
};

export default WeddingWebsite;