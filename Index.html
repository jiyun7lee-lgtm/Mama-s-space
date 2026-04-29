import streamlit as st
import numpy as np
import plotly.graph_objects as go

st.set_page_config(layout="centered")

# --- MBTI 인코딩 ---
def encode_mbti(t):
    return {
        "E": 1 if t[0]=="E" else -1,
        "S": 1 if t[1]=="S" else -1,
        "T": 1 if t[2]=="T" else -1,
        "J": 1 if t[3]=="J" else -1
    }

# --- 힘 계산 ---
def interaction(a, b, pa, pb):
    d = pb - pa
    dist = np.linalg.norm(d) + 1e-5
    dir = d / dist
    
    similarity = a["S"]*b["S"] + a["T"]*b["T"]
    complement = -(a["E"]*b["E"])
    
    attract = 0.02*(similarity + complement)
    repulse = 0.01*(abs(a["S"]-b["S"]) + abs(a["T"]-b["T"]))
    
    return (attract - repulse)*dir

# --- 시뮬레이션 ---
def simulate(t1, t2, steps=120):
    a = encode_mbti(t1)
    b = encode_mbti(t2)
    
    pa = np.array([-1.0,0.0])
    pb = np.array([1.0,0.0])
    
    va = np.array([0.0,0.12])
    vb = np.array([0.0,-0.12])
    
    xs_a, ys_a = [], []
    xs_b, ys_b = [], []
    
    for _ in range(steps):
        f = interaction(a,b,pa,pb)
        
        va += f
        vb -= f
        
        pa += va
        pb += vb
        
        xs_a.append(pa[0])
        ys_a.append(pa[1])
        xs_b.append(pb[0])
        ys_b.append(pb[1])
        
    return xs_a, ys_a, xs_b, ys_b

# --- UI ---
st.title("🌍 MBTI Planet Orbit")

col1, col2 = st.columns(2)

with col1:
    mbti1 = st.selectbox("Planet A", ["ENFP","INFJ","ISTJ","ENTP","ISFP","INTP","ESFJ","ESTP"])

with col2:
    mbti2 = st.selectbox("Planet B", ["ISTJ","ENFP","INTJ","ESFP","INFP","ENTJ","ISFJ","ESTJ"])

steps = st.slider("Time", 50, 200, 120)

if st.button("Run Simulation"):
    
    xa, ya, xb, yb = simulate(mbti1, mbti2, steps)
    
    fig = go.Figure()
    
    # 궤도
    fig.add_trace(go.Scatter(x=xa, y=ya, mode='lines',
                             line=dict(color='orange', width=2)))
    fig.add_trace(go.Scatter(x=xb, y=yb, mode='lines',
                             line=dict(color='blue', width=2)))
    
    # 현재 위치
    fig.add_trace(go.Scatter(x=[xa[-1]], y=[ya[-1]],
                             mode='markers',
                             marker=dict(size=12, color='orange')))
    fig.add_trace(go.Scatter(x=[xb[-1]], y=[yb[-1]],
                             mode='markers',
                             marker=dict(size=12, color='blue')))
    
    fig.update_layout(
        height=450,
        margin=dict(l=10,r=10,t=10,b=10),
        xaxis=dict(visible=False),
        yaxis=dict(visible=False)
    )
    
    st.plotly_chart(fig, use_container_width=True)
