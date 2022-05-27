<template>
<div class="resume">
  <div class="leftCol m_box">
    <div class="shadow"></div>
    <div class="heading" id="myselfpic">
    </div>
        <div class="section-headline">
      {{ lang.about }}
    </div>
    <div class="text2">
    <ul>
          <li>{{person.about}}</li>
          </ul>
      </div>
    <div class="section-headline">
      {{ lang.contact }}
    </div>
    <div class="item">
      <div class="icon">
        <i class="material-icons">account_circle</i>
      </div>
      <div class="text">
        <ul>
          <li> {{lang.born}} {{person.birth.year}} {{lang.bornIn}} {{person.birth.location}}</li>
        </ul>
      </div>
    </div>

    <div class="item">
      <div class="icon">
        <i class="material-icons">location_city</i>
      </div>
      <div class="text">
        <ul>
          <li>{{person.contact.city}}</li>
        </ul>
      </div>
    </div>

    <a :href="'tel:'+person.contact.phone">
      <div class="item">
        <div class="icon">
          <i class="material-icons">phone</i>
        </div>
        <div class="text">
          {{person.contact.phone}}
        </div>
      </div>
    </a>

    <a :href="'mailto:'+person.contact.email">
      <div class="item">
        <div class="icon">
          <i class="material-icons">email</i>
        </div>
        <div class="text">
          {{person.contact.email}}
        </div>
      </div>
    </a>

    <a :href="'https://github.com/'+person.contact.github" target="_blank">
      <div class="item">
        <div class="icon">
          <i class="fa fa-github"></i>
        </div>
        <div class="text">
          <span>{{person.contact.github}}</span>
        </div>
      </div>
    </a>

    <a :href="'https://linkedin.com/in/'+person.contact.linkedin" target="_blank">
      <div class="item">
        <div class="icon">
          <i class="fa fa-linkedin"></i>
        </div>
        <div class="text">
          <span>{{person.contact.linkedin}}</span>
        </div>
      </div>
    </a>

    <a :href="person.contact.website" target="_blank">
      <div class="item">
        <div class="icon">
          <i class="material-icons">language</i>
        </div>
        <div class="text">
          <span>{{person.contact.website}}</span>
        </div>
      </div>
    </a>

    <div class="item last">
      <div class="section-headline">
        {{ lang.skills }}
      </div>
      <div class="skill" v-for="skill in person.skills">
        <div class="right">
          <span>{{skill.name}}</span>
          <div class="progress">
            <div class="determinate" :style="'width: '+skill.level+'%;'">
              <i class="fa fa-circle"></i>
            </div>
          </div>
        </div>
      </div>
  </div>

      <div class="item last">
    <div class="section-headline">
        {{ lang.languages }}
      </div>
      <div class="skill" v-for="language in person.languages">
        <div class="right">
          <span>{{language.name}}</span>
          <div class="progress">
            <div class="determinate" :style="'width: '+language.level+'%;'">
              <i class="fa fa-circle"></i>
            </div>
          </div>
        </div>
      </div>
    </div>
    </div>

  <div class="rightCol">
      <div class="nameCol">
    <div class="title">
      <h2>{{person.name.first}} {{person.name.last}}</h2>
      <h4>{{person.position}}</h4>
    </div>
  </div>

    <div class="section-headline">{{ lang.education }}</div>
    <div class="block" v-for="education in person.education">
      <div class="block-helper"></div>
      <div class="headline">{{education.degree}}</div>
      <div class="subheadline">{{education.institute}}</div>
      <div class="subsubheadline">CGPA: {{education.CGPA}}</div>

      <p class="info">
        {{education.timeperiod}}, {{education.description}}
      </p>
    </div>

    <div class="section-headline">{{ lang.hobbies }}</div>
    <div class="section-subheadline">{{ lang.clicktoview }}</div>

    <div class="block" v-for="hobby in person.hobbies">
    <a :href="hobby.url" target="_blank">
      <div class="block-helper"></div>
      <div class="headline">{{hobby.name}}</h3>
      </div>
      </a>
    </div>

        <div class="section-headline">{{ lang.additional }}</div>
    <div class="block" v-for="point in person.additional">
      <div class="block-helper"></div>
      <div class="headline">{{point.point}}</h3>
      </div>
    </div>
  </div>

  <div class="farRightCol">
    <div class="section-headline">{{ lang.projects }}</div>
    <div class="section-subheadline">{{ lang.clicktoview }}</div>

    <div class="block" v-for="project in person.projects">
    <a :href="project.url" target="_blank">
      <div class="block-helper"></div>
      <div class="headline">{{project.name}}</h3>
        <div class="subheadline">Team Size: {{project.teamsize}}</div>
        <div class="subheadline">Platform: {{project.platform}}</div>
        <div class="subsubheadline">{{project.timeperiod}}</div>
        <p class="info">{{project.description}}</p>
      </div>
      </a>
    </div>
  </div>
  <div style="clear:both;"></div>
</div>
</template>

<script>
import Vue from 'vue';
import { getVueOptions } from './options';

const name = 'material-dark-projects-revised';
export default Vue.component(name, getVueOptions(name));
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less" scoped>
.resume {
    font-family: 'Roboto' !important;
    background: #cccccc;
}
a {
    cursor: pointer;
}
.description-personal {
    margin-let: 20px;
    margin-top: 20px;
    padding-right: 40px;
    text-align: justify;
    font-family: Roboto;
}
.title {
    right: 0px;
    padding-left: 0px;
    padding-top: 10px;
    bottom: 0px;
    h2 {
        text-transform: uppercase;
        display: block;
        font-size: 1em;
        -webkit-margin-start: 0;
        -webkit-margin-end: 0;
        color: white;
        color: rgba(0,0,0,0.7);
        padding-top: 0;
        margin-top: 0;
        letter-spacing: 1px;
        font-weight: 400;
    }
    div {
        margin: 0;
        padding: 0;
        line-height: 15pt;
        font-weight: 300;
        font-weight: 500;
        letter-spacing: 2px;
        letter-spacing: 3px;
        color: white;
        color: #16151c;
        color: rgba(63,61,60,0.71);
        display: block;
        font-size: 0.67em;
        font-size: 10pt;
        -webkit-margin-before: 2.33em;
        -webkit-margin-start: 0;
        -webkit-margin-end: 0;
        padding-top: 0;
        text-transform: uppercase;
        opacity: 0.8;
    }
}
.section-headline {
    text-transform: uppercase;
    font-weight: 500;
    letter-spacing: 3px;
    font-size: 10pt;
    opacity: 0.8;
    margin-left: 5px;
    margin-top: 15px;
    margin-bottom: 10px;
    color: #3f3d3c;
}
.section-subheadline {
    text-transform: uppercase;
    font-weight: 500;
    letter-spacing: 1px;
    font-size: 8pt;
    opacity: 0.6;
    margin-left: 5px;
    margin-top: 5px;
    margin-bottom: 10px;
    color: #3f3d3c;
}
.c {
    clear: both;
}
li {
    margin: 0;
    padding: 0;
    list-style-type: none;
    padding-top: 9px;
}
ul {
    margin: 0;
    padding: 0;
    list-style-type: none;
}
p {
    margin-top: 0;
    margin-bottom: 25px;
    font-family: 'Roboto', sans-serif;
    font-weight: 300;
    font-size: 10pt;
    line-height: 17pt;
}
.m_box {
    box-shadow: 0 2px 5px 0 rgba(0,0,0,0.16), 0 2px 10px 0 rgba(0,0,0,0.12);
}
.fa,
.material-icons {
    display: inline-block;
    font-style: normal;
    font-weight: normal;
    line-height: 1;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    font-size: 26px;
}
h1,
h3,
h5,
h6 {
    font-weight: 400;
    margin: 0;
}
h2 {
    font-weight: 400;
    font-weight: 500;
    margin: 0;
    font-size: 22pt;
    line-height: 37pt;
}
h4 {
    font-weight: 400;
    margin: 0;
    font-size: 12pt;
    line-height: 10pt;
    opacity: 0.6;
}
.farRightCol {
    width: 30%;
    height: 70%;
    float: left;
    display: block;
    margin-top: 75px;
    flex-direction: column;
    .block {
        width: 100%;
        position: relative;
        background-color: #ffffff;
        padding: 10px;
        margin-top: 5px;
        margin-bottom: 5px;
        display: inline-block;
        .headline {
            font-weight: 400;
            display: block;
            font-size: 13px;
            color: rgba(0,0,0,0.870588);
        }
        .subheadline {
            color: rgba(0,0,0,0.541176);
            display: block;
            font-size: 12px;
            font-weight: 300;
        }
        .subsubheadline {
            color: rgba(0,0,0,0.541176);
            display: flex;
            padding-top: 5px;
            font-size: 11px;
            font-weight: 300;
        }
        .info {
            font-size: 11px;
            color: rgba(0,0,0,0.870588);
            margin-bottom: 0;
            padding-top: 5px;
        }
        .icon {
            width: 16%;
            float: left;
            margin-left: 0;
            .fa,
            .material-icons {
                text-align: center;
                display: block;
                font-size: 30pt;
            }
        }
        .content {
            width: 80%;
            position: absolute;
            height: 96%;
            left: 5%;
            padding-right: 3%;
            text-align: left;
            display: flex;
            flex-direction: column;
            .item {
                border-bottom: 1px solid #bdbdbd;
                flex: 1;
                width: 97%;
                display: flex;
                justify-content: center;
                flex-direction: column;
                text-align: left;
                padding-top: 0;
                span {
                    color: #d8ab94;
                    margin-top: 0;
                    font-size: 10pt;
                    line-height: 16pt;
                }
                p {
                    margin-top: 5px;
                }
            }
            .item:last-of-type {
                border-bottom-style: none;
                border-bottom-style: none;
            }
        }
    }
}

.nameCol {
    width: 200%;
    height: 7%;
    float: left;
    display: flex;
    padding-left: 10px;
    flex-direction: column;
}
.rightCol {
    width: 30%;
    height: 100%;
    float: left;
    display: flex;
    padding-left: 10px;
    flex-direction: column;
    .block {
        width: 75%;
        position: relative;
        background-color: #ffffff;
        padding: 14px;
        margin-top: 5px;
        margin-bottom: 5px;
        display: inline-block;
        .headline {
            font-weight: 400;
            display: block;
            font-size: 13px;
            color: rgba(0,0,0,0.870588);
        }
        .subheadline {
            color: rgba(0,0,0,0.541176);
            display: block;
            font-size: 12px;
            font-weight: 300;
        }
        .subsubheadline {
            color: rgba(0,0,0,0.541176);
            display: flex;
            padding-top: 5px;
            font-size: 11px;
            font-weight: 300;
        }
        .info {
            font-size: 11px;
            color: rgba(0,0,0,0.870588);
            margin-bottom: 0;
            padding-top: 5px;
        }
        .icon {
            width: 16%;
            float: left;
            margin-left: 0;
            .fa,
            .material-icons {
                text-align: center;
                display: block;
                font-size: 30pt;
            }
        }
        .content {
            width: 80%;
            position: absolute;
            height: 96%;
            left: 17%;
            padding-right: 3%;
            text-align: left;
            display: flex;
            flex-direction: column;
            .item {
                border-bottom: 1px solid #bdbdbd;
                flex: 1;
                width: 97%;
                display: flex;
                justify-content: center;
                flex-direction: column;
                text-align: left;
                padding-top: 0;
                span {
                    color: #d8ab94;
                    margin-top: 0;
                    font-size: 10pt;
                    line-height: 16pt;
                }
                p {
                    margin-top: 5px;
                }
            }
            .item:last-of-type {
                border-bottom-style: none;
                border-bottom-style: none;
            }
        }
    }
}
.leftCol {
    width: 25%;
    height: 100%;
    float: left;
    padding: 0;
    text-align: left;
    color: #ffffff;
    color: rgba(255,255,255,0.59);
    background-color: #16151c;
    overflow: hidden;
    display: block;
    .section-headline {
        color: rgba(255,255,255,0.54);
    }
    a {
        color: rgba(255,255,255,0.59);
        text-decoration: none;
    }
    .heading {
        background-color: white;
        background-repeat: no-repeat;
        background-size: cover;
        background-position: center;
        position: relative;
        width: 100%;
        height: 220px;
    }
    .text2 {
            float: left;
            width: 95%;
            padding-left: 5%;
            padding-top: 0;
            padding-bottom: 10px;
            display: block;
            font-size: 13px;
            font-weight: 300;
            li {
                padding-top: 0;
                display: block;
                font-size: 12px;
                font-weight: 300;
            }
    }
    .item {
        width: 100%;
        margin-top: 5px;
        float: left;
        .fa,
        .material-icons {
            display: inherit;
            text-align: center;
        }
        .icon {
            width: 20%;
            float: left;
        }
        .text {
            float: right;
            width: 69%;
            padding-right: 10%;
            padding-top: 0;
            display: block;
            font-size: 13px;
            font-weight: 300;
            li {
                padding-top: 0;
                display: block;
                font-size: 13px;
                font-weight: 300;
            }
        }
        span {
            font-weight: 300;
        }
        .skill {
            clear: both;
            width: 97%;
            padding-top: 4px;
            .left {
                float: left;
                width: 10%;
                padding-top: 3px;
                i:nth-child(2) {
                    float: left;
                    padding-top: 4px;
                }
            }
            .right {
                float: right;
                width: 93%;
                .progress {
                    float: left;
                    position: relative;
                    height: 2px;
                    display: block;
                    width: 95%;
                    background-color: rgba(255,255,255,0.19);
                    border-radius: 2px;
                    margin: 0.5rem 0 1rem;
                    overflow: visible;
                    margin-bottom: 10px;
                    .determinate {
                        background-color: #78909c;
                        position: absolute;
                        top: 0;
                        bottom: 0;
                        .fa,
                        .material-icons {
                            font-size: 13px;
                            position: absolute;
                            top: -4px;
                            right: -2px;
                            margin-left: 50%;
                            color: white;
                        }
                    }
                }
            }
        }
    }
    .item.last .text {
        border-bottom-style: none;
        padding-bottom: 0;
    }
}
#myselfpic {
    background-image: url('../../resume/id.jpg');
    color: black;
}
#githubIcon {
    width: 25px;
    padding-left: 17px;
}
</style>
