---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---
<h2><b>Summary</b></h2>
I am a graduate student pursuing a Master's degree in Computer Science at <a target="_blank" rel="noopener noreferrer" href="https://www.purdue.edu/">Purdue University</a>. Before that, I obtained my Integrated Master of Technology degree in Computer Science at the <a target="_blank" rel="noopener noreferrer" href="https://www.iiitb.ac.in/">International Institute of Information Technology - Bangalore (IIIT-B)</a>.

#### I am looking for internship opportunities for the summer of 2023 and for full-time positions after I graduate.

<a target="_blank" rel="noopener noreferrer" href="{{ site.baseurl }}{{ site.url }}/assets/pdf/resume.pdf"><button class="button">Resume</button></a>

<h2><b>Experience</b></h2>
{% for experience in site.experience %}
  <div class="experience">
    <h4><b>{{experience.title}}</b></h4>
    <i>{{ experience.from }} - {{ experience.to }}</i>
    {{ experience.content }}
    {% for tech in experience.tech %}
      <span class="badge badge-dark">{{ tech }}</span>
    {% endfor %}
  </div>
{% endfor %}

<h2><b>Education</b></h2>
{% for education in site.education %}
  <div class="education">
    <h4><b>{{education.title}}</b></h4>
    {% if education.from and education.to %}
      <i>{{ education.from }} - {{ education.to }}</i>
    {% endif %}
    <p>
        {{ education.content }}
    </p>
  </div>
{% endfor %}

<h2><b>Publications</b></h2>
* <b>Ananth Shreekumar</b>, Biswesh Mohapatra, and Shrisha Rao. 2020. Incorporating Autonomous Bargaining Capabilities into E-Commerce Systems. In <em>Proceedings of the 20th ACM International Conference on Intelligent Virtual Agents (IVA '20)</em>. Association for Computing Machinery, New York, NY, USA, Article 51, 1–8. DOI: <a href="https://doi.org/10.1145/3383652.3423865">10.1145/3383652.3423865</a>
* Tarun Dutt, G.N.S. Prasanna, T.R. Dastidar and <b>Ananth Shreekumar</b>. Towards Artifact Rejection in Microscopic Urinalysis. In <em>Medical Imaging meets NeurIPS 2019 workshop, 33rd Conference on Neural Information Processing Systems</em>. 14th Dec, 2019. <a target="_blank" rel="noopener noreferrer" href="{{ site.baseurl }}{{ site.url }}/assets/pdf/nips_openset.pdf">[pdf]</a>

<h2><b>Relevant Course Work</b></h2>
<h4>Theory and Systems</h4>
Data Structures and Algorithms • Database Systems • Design and Analysis of Algorithms • Operating Systems • Software Engineering • Programming Languages • Introduction to Automata Theory and Computability • Computer Networks
<h4>Data Science and Machine Learning</h4>
Machine Learning • Mathematics for Machine Learning • Automatic Speech Recognition • Visual Recognition • Learning and Cognitive Systems: An Optimization Perspective • Reinforcement Learning • Artificial Intelligence