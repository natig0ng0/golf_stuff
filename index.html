import { useState, useEffect } from "react";

const DOMAINS = [
  {
    id: "market_assessment",
    label: "Market Assessment",
    short: "Market",
    color: "#8B1A2B",
    bg: "#fdf0f2",
    icon: "✓",
    category: "Strategic & Operational Planning",
  },
  {
    id: "curriculum_design",
    label: "Curriculum Design",
    short: "Curriculum Design",
    color: "#C17F24",
    bg: "#fdf6ec",
    icon: "🎓",
    category: "Curriculum & Training",
  },
  {
    id: "curriculum_delivery",
    label: "Curriculum Delivery",
    short: "Delivery",
    color: "#C17F24",
    bg: "#fdf6ec",
    icon: "📚",
    category: "Curriculum & Training",
  },
  {
    id: "work_based_learning",
    label: "Work-Based Learning",
    short: "WBL",
    color: "#C17F24",
    bg: "#fdf6ec",
    icon: "🔧",
    category: "Curriculum & Training",
  },
  {
    id: "management",
    label: "Management",
    short: "Management",
    color: "#3A6B5E",
    bg: "#edf5f3",
    icon: "⚙",
    category: "Stakeholder Management",
  },
  {
    id: "monitoring_evaluation",
    label: "Monitoring & Evaluation",
    short: "M&E",
    color: "#3A6B5E",
    bg: "#edf5f3",
    icon: "📊",
    category: "Stakeholder Management",
  },
  {
    id: "financial_sustainability",
    label: "Financial Sustainability",
    short: "Finance",
    color: "#1E4060",
    bg: "#eef3f8",
    icon: "💰",
    category: "Institutional Capacity",
  },
  {
    id: "governance",
    label: "Governance",
    short: "Governance",
    color: "#1E4060",
    bg: "#eef3f8",
    icon: "🏛",
    category: "Institutional Capacity",
  },
];

const LEVELS = [
  { value: 1, label: "Supply-Oriented", desc: "Indifferent to market; basic provision" },
  { value: 2, label: "Demand-Responsive", desc: "Actively uses market feedback" },
  { value: 3, label: "TVET-Led", desc: "Public & private TVETs engaged" },
  { value: 4, label: "Employer-Engaged", desc: "Employers driving co-design" },
  { value: 5, label: "Systems-Embedded", desc: "Government & ecosystem aligned" },
];

const RadarChart = ({ scores }) => {
  const cx = 150, cy = 150, r = 100;
  const n = DOMAINS.length;

  const getPoint = (index, value, maxR) => {
    const angle = (Math.PI * 2 * index) / n - Math.PI / 2;
    const dist = (value / 5) * maxR;
    return {
      x: cx + dist * Math.cos(angle),
      y: cy + dist * Math.sin(angle),
    };
  };

  const gridLevels = [1, 2, 3, 4, 5];
  const axisPoints = DOMAINS.map((_, i) => getPoint(i, 5, r));

  const scorePoints = DOMAINS.map((d, i) => getPoint(i, scores[d.id] || 0, r));
  const scorePath = scorePoints.map((p, i) => `${i === 0 ? "M" : "L"}${p.x},${p.y}`).join(" ") + " Z";

  return (
    <svg viewBox="0 0 300 300" className="w-full max-w-xs mx-auto">
      {gridLevels.map((lvl) => {
        const pts = DOMAINS.map((_, i) => getPoint(i, lvl, r));
        const path = pts.map((p, i) => `${i === 0 ? "M" : "L"}${p.x},${p.y}`).join(" ") + " Z";
        return <path key={lvl} d={path} fill="none" stroke="#e2e8f0" strokeWidth={lvl === 5 ? 1.5 : 0.8} />;
      })}

      {axisPoints.map((p, i) => (
        <line key={i} x1={cx} y1={cy} x2={p.x} y2={p.y} stroke="#cbd5e1" strokeWidth={0.8} />
      ))}

      <path d={scorePath} fill="rgba(139,26,43,0.15)" stroke="#8B1A2B" strokeWidth={2} />

      {scorePoints.map((p, i) => (
        scores[DOMAINS[i].id] > 0 && (
          <circle key={i} cx={p.x} cy={p.y} r={4} fill={DOMAINS[i].color} stroke="white" strokeWidth={1.5} />
        )
      ))}

      {axisPoints.map((p, i) => {
        const angle = (Math.PI * 2 * i) / n - Math.PI / 2;
        const lx = cx + (r + 22) * Math.cos(angle);
        const ly = cy + (r + 22) * Math.sin(angle);
        return (
          <text
            key={i}
            x={lx}
            y={ly}
            textAnchor="middle"
            dominantBaseline="middle"
            fontSize="8"
            fontFamily="'Georgia', serif"
            fill="#374151"
            fontWeight="500"
          >
            {DOMAINS[i].short}
          </text>
        );
      })}
    </svg>
  );
};

export default function TVETDashboard() {
  const [scores, setScores] = useState({});
  const [hoveredLevel, setHoveredLevel] = useState({});
  const [submitted, setSubmitted] = useState(false);
  const [animIn, setAnimIn] = useState(false);

  useEffect(() => {
    setTimeout(() => setAnimIn(true), 100);
  }, []);

  const scoredCount = Object.keys(scores).length;
  const totalScore = Object.values(scores).reduce((a, b) => a + b, 0);
  const avgScore = scoredCount > 0 ? (totalScore / scoredCount).toFixed(1) : "—";
  const maxPossible = DOMAINS.length * 5;
  const pct = scoredCount === DOMAINS.length ? Math.round((totalScore / maxPossible) * 100) : null;

  const handleScore = (domainId, value) => {
    setScores((prev) => ({ ...prev, [domainId]: value }));
  };

  const getScoreLabel = (avg) => {
    if (avg >= 4.5) return { text: "Systems-Embedded", color: "#1E4060" };
    if (avg >= 3.5) return { text: "Employer-Engaged", color: "#3A6B5E" };
    if (avg >= 2.5) return { text: "TVET-Led", color: "#C17F24" };
    if (avg >= 1.5) return { text: "Demand-Responsive", color: "#8B6A00" };
    return { text: "Supply-Oriented", color: "#8B1A2B" };
  };

  const overallLabel = scoredCount === DOMAINS.length ? getScoreLabel(parseFloat(avgScore)) : null;

  return (
    <div
      style={{
        minHeight: "100vh",
        background: "#f8f5f0",
        fontFamily: "'Georgia', 'Times New Roman', serif",
        opacity: animIn ? 1 : 0,
        transition: "opacity 0.6s ease",
      }}
    >
      {/* Header */}
      <div
        style={{
          background: "linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f3460 100%)",
          padding: "2.5rem 2rem 2rem",
          position: "relative",
          overflow: "hidden",
        }}
      >
        <div
          style={{
            position: "absolute",
            top: 0, left: 0, right: 0, bottom: 0,
            backgroundImage: "repeating-linear-gradient(45deg, rgba(255,255,255,0.02) 0px, rgba(255,255,255,0.02) 1px, transparent 1px, transparent 12px)",
          }}
        />
        <div style={{ position: "relative", maxWidth: 900, margin: "0 auto" }}>
          <div style={{ display: "flex", alignItems: "center", gap: "0.75rem", marginBottom: "0.5rem" }}>
            <div style={{ width: 3, height: 28, background: "#C17F24", borderRadius: 2 }} />
            <span style={{ color: "#C17F24", fontSize: "0.7rem", letterSpacing: "0.2em", fontFamily: "sans-serif", fontWeight: 700, textTransform: "uppercase" }}>
              Assessment Framework
            </span>
          </div>
          <h1 style={{ color: "white", fontSize: "clamp(1.4rem, 3vw, 2rem)", margin: "0 0 0.5rem", fontWeight: 400, letterSpacing: "-0.01em" }}>
            TVET Institutional Scorecard
          </h1>
          <p style={{ color: "#94a3b8", fontSize: "0.85rem", margin: 0, fontFamily: "sans-serif" }}>
            Rate each domain across 8 key institutional levers of change
          </p>
        </div>
      </div>

      <div style={{ maxWidth: 900, margin: "0 auto", padding: "1.5rem 1rem 3rem" }}>
        <div style={{ display: "grid", gridTemplateColumns: "1fr", gap: "1rem" }}>

          {/* Score Cards */}
          <div style={{ display: "grid", gridTemplateColumns: "repeat(auto-fill, minmax(260px, 1fr))", gap: "1rem" }}>
            {DOMAINS.map((domain, di) => {
              const current = scores[domain.id];
              return (
                <div
                  key={domain.id}
                  style={{
                    background: "white",
                    borderRadius: 12,
                    overflow: "hidden",
                    boxShadow: current ? `0 2px 12px ${domain.color}22` : "0 1px 4px rgba(0,0,0,0.08)",
                    border: `1px solid ${current ? domain.color + "44" : "#e5e7eb"}`,
                    transition: "all 0.3s ease",
                    opacity: animIn ? 1 : 0,
                    transform: animIn ? "translateY(0)" : "translateY(12px)",
                    transitionDelay: `${di * 0.06}s`,
                  }}
                >
                  {/* Card Header */}
                  <div
                    style={{
                      background: domain.bg,
                      borderBottom: `2px solid ${domain.color}`,
                      padding: "0.75rem 1rem",
                      display: "flex",
                      alignItems: "center",
                      justifyContent: "space-between",
                    }}
                  >
                    <div>
                      <div style={{ fontSize: "0.6rem", color: domain.color, fontFamily: "sans-serif", fontWeight: 700, letterSpacing: "0.12em", textTransform: "uppercase", marginBottom: 2 }}>
                        {domain.category}
                      </div>
                      <div style={{ fontSize: "0.95rem", fontWeight: 600, color: "#1a1a1a" }}>
                        {domain.label}
                      </div>
                    </div>
                    <div
                      style={{
                        width: 36, height: 36, borderRadius: 8,
                        background: current ? domain.color : "#f1f5f9",
                        display: "flex", alignItems: "center", justifyContent: "center",
                        fontSize: "1rem",
                        transition: "background 0.3s ease",
                      }}
                    >
                      {current ? (
                        <span style={{ color: "white", fontWeight: 700, fontSize: "0.9rem", fontFamily: "sans-serif" }}>{current}</span>
                      ) : (
                        <span style={{ fontSize: "1rem" }}>—</span>
                      )}
                    </div>
                  </div>

                  {/* Level Buttons */}
                  <div style={{ padding: "0.75rem 1rem" }}>
                    <div style={{ display: "flex", gap: "0.3rem", marginBottom: "0.5rem" }}>
                      {LEVELS.map((lvl) => {
                        const isSelected = current === lvl.value;
                        const isHovered = hoveredLevel[domain.id] === lvl.value;
                        return (
                          <button
                            key={lvl.value}
                            onClick={() => handleScore(domain.id, lvl.value)}
                            onMouseEnter={() => setHoveredLevel((p) => ({ ...p, [domain.id]: lvl.value }))}
                            onMouseLeave={() => setHoveredLevel((p) => ({ ...p, [domain.id]: null }))}
                            style={{
                              flex: 1,
                              height: 28,
                              border: "none",
                              borderRadius: 5,
                              cursor: "pointer",
                              background: isSelected ? domain.color : isHovered ? domain.color + "33" : "#f1f5f9",
                              color: isSelected ? "white" : domain.color,
                              fontWeight: 700,
                              fontSize: "0.8rem",
                              fontFamily: "sans-serif",
                              transition: "all 0.15s ease",
                              transform: isSelected ? "scale(1.05)" : "scale(1)",
                            }}
                          >
                            {lvl.value}
                          </button>
                        );
                      })}
                    </div>

                    {/* Level description */}
                    <div style={{ minHeight: 28 }}>
                      {(hoveredLevel[domain.id] || current) && (
                        <div style={{ fontSize: "0.7rem", color: "#64748b", fontFamily: "sans-serif", lineHeight: 1.4 }}>
                          <span style={{ fontWeight: 700, color: domain.color }}>
                            {LEVELS[(hoveredLevel[domain.id] || current) - 1].label}:
                          </span>{" "}
                          {LEVELS[(hoveredLevel[domain.id] || current) - 1].desc}
                        </div>
                      )}
                    </div>
                  </div>
                </div>
              );
            })}
          </div>

          {/* Summary Panel */}
          <div
            style={{
              display: "grid",
              gridTemplateColumns: "1fr 1fr",
              gap: "1rem",
              marginTop: "0.5rem",
            }}
          >
            {/* Radar */}
            <div
              style={{
                background: "white",
                borderRadius: 12,
                padding: "1.25rem",
                boxShadow: "0 1px 4px rgba(0,0,0,0.08)",
                border: "1px solid #e5e7eb",
              }}
            >
              <div style={{ fontSize: "0.65rem", color: "#94a3b8", fontFamily: "sans-serif", fontWeight: 700, letterSpacing: "0.12em", textTransform: "uppercase", marginBottom: "0.75rem" }}>
                Domain Profile
              </div>
              <RadarChart scores={scores} />
              <div style={{ display: "flex", flexWrap: "wrap", gap: "0.35rem", marginTop: "0.75rem", justifyContent: "center" }}>
                {DOMAINS.map((d) => (
                  <div key={d.id} style={{ display: "flex", alignItems: "center", gap: 4, fontSize: "0.6rem", fontFamily: "sans-serif", color: "#64748b" }}>
                    <div style={{ width: 6, height: 6, borderRadius: "50%", background: d.color }} />
                    {d.short}
                  </div>
                ))}
              </div>
            </div>

            {/* Score Summary */}
            <div style={{ display: "flex", flexDirection: "column", gap: "0.75rem" }}>
              {/* Overall */}
              <div
                style={{
                  background: "linear-gradient(135deg, #1a1a2e, #0f3460)",
                  borderRadius: 12,
                  padding: "1.25rem",
                  color: "white",
                  flex: 1,
                }}
              >
                <div style={{ fontSize: "0.65rem", color: "#94a3b8", fontFamily: "sans-serif", fontWeight: 700, letterSpacing: "0.12em", textTransform: "uppercase", marginBottom: "0.75rem" }}>
                  Overall Score
                </div>
                <div style={{ fontSize: "3rem", fontWeight: 400, lineHeight: 1, marginBottom: "0.25rem" }}>
                  {avgScore}
                  <span style={{ fontSize: "1rem", color: "#94a3b8", marginLeft: 4, fontFamily: "sans-serif" }}>/5</span>
                </div>
                {overallLabel && (
                  <div style={{ fontSize: "0.85rem", color: "#C17F24", fontWeight: 600, marginTop: "0.25rem" }}>
                    {overallLabel.text}
                  </div>
                )}
                {pct !== null && (
                  <div style={{ marginTop: "0.75rem" }}>
                    <div style={{ display: "flex", justifyContent: "space-between", fontSize: "0.65rem", fontFamily: "sans-serif", color: "#94a3b8", marginBottom: 4 }}>
                      <span>Total: {totalScore}/{maxPossible}</span>
                      <span>{pct}%</span>
                    </div>
                    <div style={{ height: 6, background: "rgba(255,255,255,0.1)", borderRadius: 3, overflow: "hidden" }}>
                      <div
                        style={{
                          height: "100%",
                          width: `${pct}%`,
                          background: "linear-gradient(90deg, #C17F24, #e8a84c)",
                          borderRadius: 3,
                          transition: "width 0.5s ease",
                        }}
                      />
                    </div>
                  </div>
                )}
                <div style={{ fontSize: "0.65rem", fontFamily: "sans-serif", color: "#475569", marginTop: "0.75rem" }}>
                  {scoredCount}/{DOMAINS.length} domains rated
                </div>
              </div>

              {/* Per-domain scores */}
              <div
                style={{
                  background: "white",
                  borderRadius: 12,
                  padding: "1.25rem",
                  boxShadow: "0 1px 4px rgba(0,0,0,0.08)",
                  border: "1px solid #e5e7eb",
                  flex: 2,
                }}
              >
                <div style={{ fontSize: "0.65rem", color: "#94a3b8", fontFamily: "sans-serif", fontWeight: 700, letterSpacing: "0.12em", textTransform: "uppercase", marginBottom: "0.75rem" }}>
                  Domain Breakdown
                </div>
                <div style={{ display: "flex", flexDirection: "column", gap: "0.4rem" }}>
                  {DOMAINS.map((d) => {
                    const s = scores[d.id] || 0;
                    return (
                      <div key={d.id} style={{ display: "flex", alignItems: "center", gap: "0.5rem" }}>
                        <div style={{ fontSize: "0.65rem", fontFamily: "sans-serif", color: "#374151", width: 90, flexShrink: 0, lineHeight: 1.2 }}>
                          {d.short}
                        </div>
                        <div style={{ flex: 1, height: 8, background: "#f1f5f9", borderRadius: 4, overflow: "hidden" }}>
                          <div
                            style={{
                              height: "100%",
                              width: `${(s / 5) * 100}%`,
                              background: s > 0 ? d.color : "transparent",
                              borderRadius: 4,
                              transition: "width 0.4s ease",
                            }}
                          />
                        </div>
                        <div style={{ fontSize: "0.7rem", fontFamily: "sans-serif", fontWeight: 700, color: s > 0 ? d.color : "#cbd5e1", width: 16, textAlign: "right" }}>
                          {s || "—"}
                        </div>
                      </div>
                    );
                  })}
                </div>
              </div>

              {/* Reset */}
              {scoredCount > 0 && (
                <button
                  onClick={() => setScores({})}
                  style={{
                    background: "transparent",
                    border: "1px solid #e5e7eb",
                    borderRadius: 8,
                    padding: "0.6rem 1rem",
                    fontSize: "0.75rem",
                    fontFamily: "sans-serif",
                    color: "#94a3b8",
                    cursor: "pointer",
                    transition: "all 0.15s ease",
                  }}
                  onMouseEnter={(e) => { e.target.style.borderColor = "#8B1A2B"; e.target.style.color = "#8B1A2B"; }}
                  onMouseLeave={(e) => { e.target.style.borderColor = "#e5e7eb"; e.target.style.color = "#94a3b8"; }}
                >
                  Reset scores
                </button>
              )}
            </div>
          </div>

          {/* Level Legend */}
          <div
            style={{
              background: "white",
              borderRadius: 12,
              padding: "1.25rem",
              boxShadow: "0 1px 4px rgba(0,0,0,0.08)",
              border: "1px solid #e5e7eb",
            }}
          >
            <div style={{ fontSize: "0.65rem", color: "#94a3b8", fontFamily: "sans-serif", fontWeight: 700, letterSpacing: "0.12em", textTransform: "uppercase", marginBottom: "1rem" }}>
              Scoring Scale
            </div>
            <div style={{ display: "grid", gridTemplateColumns: "repeat(5, 1fr)", gap: "0.75rem" }}>
              {LEVELS.map((lvl) => (
                <div key={lvl.value} style={{ textAlign: "center" }}>
                  <div
                    style={{
                      width: 36, height: 36,
                      borderRadius: "50%",
                      background: `hsl(${200 + lvl.value * 20}, 60%, ${55 - lvl.value * 6}%)`,
                      color: "white",
                      fontWeight: 700,
                      fontSize: "1rem",
                      fontFamily: "sans-serif",
                      display: "flex",
                      alignItems: "center",
                      justifyContent: "center",
                      margin: "0 auto 0.4rem",
                    }}
                  >
                    {lvl.value}
                  </div>
                  <div style={{ fontSize: "0.7rem", fontWeight: 700, color: "#374151", marginBottom: 2 }}>{lvl.label}</div>
                  <div style={{ fontSize: "0.6rem", color: "#94a3b8", fontFamily: "sans-serif", lineHeight: 1.3 }}>{lvl.desc}</div>
                </div>
              ))}
            </div>
          </div>
        </div>
      </div>
    </div>
  );
}
