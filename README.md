# api documentation for  [zxcvbn (v4.4.2)](https://github.com/dropbox/zxcvbn#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-zxcvbn.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-zxcvbn) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-zxcvbn.svg)](https://travis-ci.org/npmdoc/node-npmdoc-zxcvbn)
#### realistic password strength estimation

[![NPM](https://nodei.co/npm/zxcvbn.png?downloads=true)](https://www.npmjs.com/package/zxcvbn)

[![apidoc](https://npmdoc.github.io/node-npmdoc-zxcvbn/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-zxcvbn_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-zxcvbn/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-zxcvbn/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-zxcvbn/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Dan Wheeler"
    },
    "bugs": {
        "url": "https://github.com/dropbox/zxcvbn/issues"
    },
    "dependencies": {},
    "description": "realistic password strength estimation",
    "devDependencies": {
        "browserify": "^11.0.1",
        "coffee-coverage": "^0.6.3",
        "coffee-script": "^1.10.0",
        "coffeeify": "^1.1.0",
        "coffeetape": "^1.0.1",
        "exorcist": "^0.4.0",
        "faucet": "^0.0.1",
        "istanbul": "^0.3.18",
        "tape": "^4.2.0",
        "uglifyify": "^3.0.1",
        "watchify": "^3.3.1",
        "zuul": "^3.4.0"
    },
    "directories": {},
    "dist": {
        "shasum": "28ec17cf09743edcab056ddd8b1b06262cc73c30",
        "tarball": "https://registry.npmjs.org/zxcvbn/-/zxcvbn-4.4.2.tgz"
    },
    "gitHead": "f0735425180b130d6c57efbc044a47c0c8f1fd65",
    "homepage": "https://github.com/dropbox/zxcvbn#readme",
    "keywords": [
        "password",
        "passphrase",
        "security",
        "authentication",
        "strength",
        "meter",
        "quality",
        "estimation",
        "pattern",
        "cracking",
        "scoring",
        "entropy",
        "bruteforce"
    ],
    "license": "MIT",
    "main": "lib/main.js",
    "maintainers": [
        {
            "name": "wheels",
            "email": "dan@dropbox.com"
        }
    ],
    "name": "zxcvbn",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/dropbox/zxcvbn.git"
    },
    "scripts": {
        "build": "npm run build-lib ; npm run build-dist",
        "build-dist": "browserify --debug  --standalone zxcvbn -t coffeeify --extension='.coffee' -t uglifyify src/main.coffee |   exorcist --base . dist/zxcvbn.js.map >| dist/zxcvbn.js",
        "build-lib": "coffee -o lib --compile --bare --map src/*.coffee",
        "prepublish": "npm run build",
        "test": "coffeetape test/*.coffee | faucet",
        "test-saucelabs": "zuul -- test/*.coffee",
        "watch": "npm run watch-lib & npm run watch-dist",
        "watch-dist": "watchify --debug -v --standalone zxcvbn -t coffeeify --extension='.coffee' -t uglifyify src/main.coffee -o 'exorcist --base . dist/zxcvbn.js.map >| dist/zxcvbn.js'",
        "watch-lib": "coffee -o lib --compile --bare --map --watch src/*.coffee"
    },
    "version": "4.4.2"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module zxcvbn](#apidoc.module.zxcvbn)
1.  object <span class="apidocSignatureSpan">zxcvbn.</span>feedback
1.  object <span class="apidocSignatureSpan">zxcvbn.</span>matching
1.  object <span class="apidocSignatureSpan">zxcvbn.</span>scoring
1.  object <span class="apidocSignatureSpan">zxcvbn.</span>time_estimates

#### [module zxcvbn.feedback](#apidoc.module.zxcvbn.feedback)
1.  [function <span class="apidocSignatureSpan">zxcvbn.feedback.</span>get_dictionary_match_feedback (match, is_sole_match)](#apidoc.element.zxcvbn.feedback.get_dictionary_match_feedback)
1.  [function <span class="apidocSignatureSpan">zxcvbn.feedback.</span>get_feedback (score, sequence)](#apidoc.element.zxcvbn.feedback.get_feedback)
1.  [function <span class="apidocSignatureSpan">zxcvbn.feedback.</span>get_match_feedback (match, is_sole_match)](#apidoc.element.zxcvbn.feedback.get_match_feedback)
1.  object <span class="apidocSignatureSpan">zxcvbn.feedback.</span>default_feedback

#### [module zxcvbn.matching](#apidoc.module.zxcvbn.matching)
1.  [function <span class="apidocSignatureSpan">zxcvbn.matching.</span>date_match (password)](#apidoc.element.zxcvbn.matching.date_match)
1.  [function <span class="apidocSignatureSpan">zxcvbn.matching.</span>dictionary_match (password, _ranked_dictionaries)](#apidoc.element.zxcvbn.matching.dictionary_match)
1.  [function <span class="apidocSignatureSpan">zxcvbn.matching.</span>empty (obj)](#apidoc.element.zxcvbn.matching.empty)
1.  [function <span class="apidocSignatureSpan">zxcvbn.matching.</span>enumerate_l33t_subs (table)](#apidoc.element.zxcvbn.matching.enumerate_l33t_subs)
1.  [function <span class="apidocSignatureSpan">zxcvbn.matching.</span>extend (lst, lst2)](#apidoc.element.zxcvbn.matching.extend)
1.  [function <span class="apidocSignatureSpan">zxcvbn.matching.</span>l33t_match (password, _ranked_dictionaries, _l33t_table)](#apidoc.element.zxcvbn.matching.l33t_match)
1.  [function <span class="apidocSignatureSpan">zxcvbn.matching.</span>map_ints_to_dm (ints)](#apidoc.element.zxcvbn.matching.map_ints_to_dm)
1.  [function <span class="apidocSignatureSpan">zxcvbn.matching.</span>map_ints_to_dmy (ints)](#apidoc.element.zxcvbn.matching.map_ints_to_dmy)
1.  [function <span class="apidocSignatureSpan">zxcvbn.matching.</span>mod (n, m)](#apidoc.element.zxcvbn.matching.mod)
1.  [function <span class="apidocSignatureSpan">zxcvbn.matching.</span>omnimatch (password)](#apidoc.element.zxcvbn.matching.omnimatch)
1.  [function <span class="apidocSignatureSpan">zxcvbn.matching.</span>regex_match (password, _regexen)](#apidoc.element.zxcvbn.matching.regex_match)
1.  [function <span class="apidocSignatureSpan">zxcvbn.matching.</span>relevant_l33t_subtable (password, table)](#apidoc.element.zxcvbn.matching.relevant_l33t_subtable)
1.  [function <span class="apidocSignatureSpan">zxcvbn.matching.</span>repeat_match (password)](#apidoc.element.zxcvbn.matching.repeat_match)
1.  [function <span class="apidocSignatureSpan">zxcvbn.matching.</span>reverse_dictionary_match (password, _ranked_dictionaries)](#apidoc.element.zxcvbn.matching.reverse_dictionary_match)
1.  [function <span class="apidocSignatureSpan">zxcvbn.matching.</span>sequence_match (password)](#apidoc.element.zxcvbn.matching.sequence_match)
1.  [function <span class="apidocSignatureSpan">zxcvbn.matching.</span>set_user_input_dictionary (ordered_list)](#apidoc.element.zxcvbn.matching.set_user_input_dictionary)
1.  [function <span class="apidocSignatureSpan">zxcvbn.matching.</span>sorted (matches)](#apidoc.element.zxcvbn.matching.sorted)
1.  [function <span class="apidocSignatureSpan">zxcvbn.matching.</span>spatial_match (password, _graphs)](#apidoc.element.zxcvbn.matching.spatial_match)
1.  [function <span class="apidocSignatureSpan">zxcvbn.matching.</span>spatial_match_helper (password, graph, graph_name)](#apidoc.element.zxcvbn.matching.spatial_match_helper)
1.  [function <span class="apidocSignatureSpan">zxcvbn.matching.</span>translate (string, chr_map)](#apidoc.element.zxcvbn.matching.translate)
1.  [function <span class="apidocSignatureSpan">zxcvbn.matching.</span>two_to_four_digit_year (year)](#apidoc.element.zxcvbn.matching.two_to_four_digit_year)
1.  number <span class="apidocSignatureSpan">zxcvbn.matching.</span>MAX_DELTA
1.  object <span class="apidocSignatureSpan">zxcvbn.matching.</span>SHIFTED_RX

#### [module zxcvbn.scoring](#apidoc.module.zxcvbn.scoring)
1.  [function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>bruteforce_guesses (match)](#apidoc.element.zxcvbn.scoring.bruteforce_guesses)
1.  [function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>date_guesses (match)](#apidoc.element.zxcvbn.scoring.date_guesses)
1.  [function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>dictionary_guesses (match)](#apidoc.element.zxcvbn.scoring.dictionary_guesses)
1.  [function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>estimate_guesses (match, password)](#apidoc.element.zxcvbn.scoring.estimate_guesses)
1.  [function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>factorial (n)](#apidoc.element.zxcvbn.scoring.factorial)
1.  [function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>l33t_variations (match)](#apidoc.element.zxcvbn.scoring.l33t_variations)
1.  [function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>log10 (n)](#apidoc.element.zxcvbn.scoring.log10)
1.  [function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>log2 (n)](#apidoc.element.zxcvbn.scoring.log2)
1.  [function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>most_guessable_match_sequence (password, matches, _exclude_additive)](#apidoc.element.zxcvbn.scoring.most_guessable_match_sequence)
1.  [function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>nCk (n, k)](#apidoc.element.zxcvbn.scoring.nCk)
1.  [function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>regex_guesses (match)](#apidoc.element.zxcvbn.scoring.regex_guesses)
1.  [function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>repeat_guesses (match)](#apidoc.element.zxcvbn.scoring.repeat_guesses)
1.  [function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>sequence_guesses (match)](#apidoc.element.zxcvbn.scoring.sequence_guesses)
1.  [function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>spatial_guesses (match)](#apidoc.element.zxcvbn.scoring.spatial_guesses)
1.  [function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>uppercase_variations (match)](#apidoc.element.zxcvbn.scoring.uppercase_variations)
1.  number <span class="apidocSignatureSpan">zxcvbn.scoring.</span>KEYBOARD_AVERAGE_DEGREE
1.  number <span class="apidocSignatureSpan">zxcvbn.scoring.</span>KEYBOARD_STARTING_POSITIONS
1.  number <span class="apidocSignatureSpan">zxcvbn.scoring.</span>KEYPAD_AVERAGE_DEGREE
1.  number <span class="apidocSignatureSpan">zxcvbn.scoring.</span>KEYPAD_STARTING_POSITIONS
1.  number <span class="apidocSignatureSpan">zxcvbn.scoring.</span>MIN_YEAR_SPACE
1.  number <span class="apidocSignatureSpan">zxcvbn.scoring.</span>REFERENCE_YEAR
1.  object <span class="apidocSignatureSpan">zxcvbn.scoring.</span>ALL_LOWER
1.  object <span class="apidocSignatureSpan">zxcvbn.scoring.</span>ALL_UPPER
1.  object <span class="apidocSignatureSpan">zxcvbn.scoring.</span>END_UPPER
1.  object <span class="apidocSignatureSpan">zxcvbn.scoring.</span>START_UPPER

#### [module zxcvbn.time_estimates](#apidoc.module.zxcvbn.time_estimates)
1.  [function <span class="apidocSignatureSpan">zxcvbn.time_estimates.</span>display_time (seconds)](#apidoc.element.zxcvbn.time_estimates.display_time)
1.  [function <span class="apidocSignatureSpan">zxcvbn.time_estimates.</span>estimate_attack_times (guesses)](#apidoc.element.zxcvbn.time_estimates.estimate_attack_times)
1.  [function <span class="apidocSignatureSpan">zxcvbn.time_estimates.</span>guesses_to_score (guesses)](#apidoc.element.zxcvbn.time_estimates.guesses_to_score)



# <a name="apidoc.module.zxcvbn"></a>[module zxcvbn](#apidoc.module.zxcvbn)



# <a name="apidoc.module.zxcvbn.feedback"></a>[module zxcvbn.feedback](#apidoc.module.zxcvbn.feedback)

#### <a name="apidoc.element.zxcvbn.feedback.get_dictionary_match_feedback"></a>[function <span class="apidocSignatureSpan">zxcvbn.feedback.</span>get_dictionary_match_feedback (match, is_sole_match)](#apidoc.element.zxcvbn.feedback.get_dictionary_match_feedback)
- description and source-code
```javascript
get_dictionary_match_feedback = function (match, is_sole_match) {
  var ref, result, suggestions, warning, word;
  warning = match.dictionary_name === 'passwords' ? is_sole_match && !match.l33t && !match.reversed ? match.rank <= 10 ? 'This is
 a top-10 common password' : match.rank <= 100 ? 'This is a top-100 common password' : 'This is a very common password' : match.
guesses_log10 <= 4 ? 'This is similar to a commonly used password' : void 0 : match.dictionary_name === 'english_wikipedia' ? is_sole_match
 ? 'A word by itself is easy to guess' : void 0 : (ref = match.dictionary_name) === 'surnames' || ref === 'male_names' || ref === '
female_names' ? is_sole_match ? 'Names and surnames by themselves are easy to guess' : 'Common names and surnames are easy to guess
' : '';
  suggestions = [];
  word = match.token;
  if (word.match(scoring.START_UPPER)) {
    suggestions.push("Capitalization doesn't help very much");
  } else if (word.match(scoring.ALL_UPPER) && word.toLowerCase() !== word) {
    suggestions.push("All-uppercase is almost as easy to guess as all-lowercase");
  }
  if (match.reversed && match.token.length >= 4) {
    suggestions.push("Reversed words aren't much harder to guess");
  }
  if (match.l33t) {
    suggestions.push("Predictable substitutions like '@' instead of 'a' don't help very much");
  }
  result = {
    warning: warning,
    suggestions: suggestions
  };
  return result;
}
```
- example usage
```shell
...
  }
  return feedback;
},
get_match_feedback: function(match, is_sole_match) {
  var layout, warning;
  switch (match.pattern) {
    case 'dictionary':
      return this.get_dictionary_match_feedback(match, is_sole_match);
    case 'spatial':
      layout = match.graph.toUpperCase();
      warning = match.turns === 1 ? 'Straight rows of keys are easy to guess' : 'Short keyboard patterns are easy to guess';
      return {
        warning: warning,
        suggestions: ['Use a longer keyboard pattern with more turns']
      };
...
```

#### <a name="apidoc.element.zxcvbn.feedback.get_feedback"></a>[function <span class="apidocSignatureSpan">zxcvbn.feedback.</span>get_feedback (score, sequence)](#apidoc.element.zxcvbn.feedback.get_feedback)
- description and source-code
```javascript
get_feedback = function (score, sequence) {
  var extra_feedback, i, len, longest_match, match, ref;
  if (sequence.length === 0) {
    return this.default_feedback;
  }
  if (score > 2) {
    return {
      warning: '',
      suggestions: []
    };
  }
  longest_match = sequence[0];
  ref = sequence.slice(1);
  for (i = 0, len = ref.length; i < len; i++) {
    match = ref[i];
    if (match.token.length > longest_match.token.length) {
      longest_match = match;
    }
  }
  feedback = this.get_match_feedback(longest_match, sequence.length === 1);
  extra_feedback = 'Add another word or two. Uncommon words are better.';
  if (feedback != null) {
    feedback.suggestions.unshift(extra_feedback);
    if (feedback.warning == null) {
      feedback.warning = '';
    }
  } else {
    feedback = {
      warning: '',
      suggestions: [extra_feedback]
    };
  }
  return feedback;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.zxcvbn.feedback.get_match_feedback"></a>[function <span class="apidocSignatureSpan">zxcvbn.feedback.</span>get_match_feedback (match, is_sole_match)](#apidoc.element.zxcvbn.feedback.get_match_feedback)
- description and source-code
```javascript
get_match_feedback = function (match, is_sole_match) {
  var layout, warning;
  switch (match.pattern) {
    case 'dictionary':
      return this.get_dictionary_match_feedback(match, is_sole_match);
    case 'spatial':
      layout = match.graph.toUpperCase();
      warning = match.turns === 1 ? 'Straight rows of keys are easy to guess' : 'Short keyboard patterns are easy to guess';
      return {
        warning: warning,
        suggestions: ['Use a longer keyboard pattern with more turns']
      };
    case 'repeat':
      warning = match.base_token.length === 1 ? 'Repeats like "aaa" are easy to guess' : 'Repeats like "abcabcabc" are only slightly
 harder to guess than "abc"';
      return {
        warning: warning,
        suggestions: ['Avoid repeated words and characters']
      };
    case 'sequence':
      return {
        warning: "Sequences like abc or 6543 are easy to guess",
        suggestions: ['Avoid sequences']
      };
    case 'regex':
      if (match.regex_name === 'recent_year') {
        return {
          warning: "Recent years are easy to guess",
          suggestions: ['Avoid recent years', 'Avoid years that are associated with you']
        };
      }
      break;
    case 'date':
      return {
        warning: "Dates are often easy to guess",
        suggestions: ['Avoid dates and years that are associated with you']
      };
  }
}
```
- example usage
```shell
...
ref = sequence.slice(1);
for (i = 0, len = ref.length; i < len; i++) {
  match = ref[i];
  if (match.token.length > longest_match.token.length) {
    longest_match = match;
  }
}
feedback = this.get_match_feedback(longest_match, sequence.length === 1);
extra_feedback = 'Add another word or two. Uncommon words are better.';
if (feedback != null) {
  feedback.suggestions.unshift(extra_feedback);
  if (feedback.warning == null) {
    feedback.warning = '';
  }
} else {
...
```



# <a name="apidoc.module.zxcvbn.matching"></a>[module zxcvbn.matching](#apidoc.module.zxcvbn.matching)

#### <a name="apidoc.element.zxcvbn.matching.date_match"></a>[function <span class="apidocSignatureSpan">zxcvbn.matching.</span>date_match (password)](#apidoc.element.zxcvbn.matching.date_match)
- description and source-code
```javascript
date_match = function (password) {
  var best_candidate, candidate, candidates, distance, dmy, i, j, k, l, len1, len2, matches, maybe_date_no_separator, maybe_date_with_separator
, metric, min_distance, o, p, q, r, ref, ref1, ref2, ref3, ref4, ref5, ref6, ref7, ref8, ref9, rx_match, s, t, token;
  matches = [];
  maybe_date_no_separator = /^\d{4,8}$/;
  maybe_date_with_separator = /^(\d{1,4})([\s\/\\_.-])(\d{1,2})\2(\d{1,4})$/;
  for (i = o = 0, ref = password.length - 4; 0 <= ref ? o <= ref : o >= ref; i = 0 <= ref ? ++o : --o) {
    for (j = p = ref1 = i + 3, ref2 = i + 7; ref1 <= ref2 ? p <= ref2 : p >= ref2; j = ref1 <= ref2 ? ++p : --p) {
      if (j >= password.length) {
        break;
      }
      token = password.slice(i, +j + 1 || 9e9);
      if (!maybe_date_no_separator.exec(token)) {
        continue;
      }
      candidates = [];
      ref3 = DATE_SPLITS[token.length];
      for (q = 0, len1 = ref3.length; q < len1; q++) {
        ref4 = ref3[q], k = ref4[0], l = ref4[1];
        dmy = this.map_ints_to_dmy([parseInt(token.slice(0, k)), parseInt(token.slice(k, l)), parseInt(token.slice(l))]);
        if (dmy != null) {
          candidates.push(dmy);
        }
      }
      if (!(candidates.length > 0)) {
        continue;
      }
      best_candidate = candidates[0];
      metric = function(candidate) {
        return Math.abs(candidate.year - scoring.REFERENCE_YEAR);
      };
      min_distance = metric(candidates[0]);
      ref5 = candidates.slice(1);
      for (r = 0, len2 = ref5.length; r < len2; r++) {
        candidate = ref5[r];
        distance = metric(candidate);
        if (distance < min_distance) {
          ref6 = [candidate, distance], best_candidate = ref6[0], min_distance = ref6[1];
        }
      }
      matches.push({
        pattern: 'date',
        token: token,
        i: i,
        j: j,
        separator: '',
        year: best_candidate.year,
        month: best_candidate.month,
        day: best_candidate.day
      });
    }
  }
  for (i = s = 0, ref7 = password.length - 6; 0 <= ref7 ? s <= ref7 : s >= ref7; i = 0 <= ref7 ? ++s : --s) {
    for (j = t = ref8 = i + 5, ref9 = i + 9; ref8 <= ref9 ? t <= ref9 : t >= ref9; j = ref8 <= ref9 ? ++t : --t) {
      if (j >= password.length) {
        break;
      }
      token = password.slice(i, +j + 1 || 9e9);
      rx_match = maybe_date_with_separator.exec(token);
      if (rx_match == null) {
        continue;
      }
      dmy = this.map_ints_to_dmy([parseInt(rx_match[1]), parseInt(rx_match[3]), parseInt(rx_match[4])]);
      if (dmy == null) {
        continue;
      }
      matches.push({
        pattern: 'date',
        token: token,
        i: i,
        j: j,
        separator: rx_match[2],
        year: dmy.year,
        month: dmy.month,
        day: dmy.day
      });
    }
  }
  return this.sorted(matches.filter(function(match) {
    var is_submatch, len3, other_match, u;
    is_submatch = false;
    for (u = 0, len3 = matches.length; u < len3; u++) {
      other_match = matches[u];
      if (match === other_match) {
        continue;
      }
      if (other_match.i <= match.i && other_match.j >= match.j) {
        is_submatch = true;
        break;
      }
    }
    return !is_submatch;
  }));
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.zxcvbn.matching.dictionary_match"></a>[function <span class="apidocSignatureSpan">zxcvbn.matching.</span>dictionary_match (password, _ranked_dictionaries)](#apidoc.element.zxcvbn.matching.dictionary_match)
- description and source-code
```javascript
dictionary_match = function (password, _ranked_dictionaries) {
  var dictionary_name, i, j, len, matches, o, p, password_lower, rank, ranked_dict, ref, ref1, ref2, word;
  if (_ranked_dictionaries == null) {
    _ranked_dictionaries = RANKED_DICTIONARIES;
  }
  matches = [];
  len = password.length;
  password_lower = password.toLowerCase();
  for (dictionary_name in _ranked_dictionaries) {
    ranked_dict = _ranked_dictionaries[dictionary_name];
    for (i = o = 0, ref = len; 0 <= ref ? o < ref : o > ref; i = 0 <= ref ? ++o : --o) {
      for (j = p = ref1 = i, ref2 = len; ref1 <= ref2 ? p < ref2 : p > ref2; j = ref1 <= ref2 ? ++p : --p) {
        if (password_lower.slice(i, +j + 1 || 9e9) in ranked_dict) {
          word = password_lower.slice(i, +j + 1 || 9e9);
          rank = ranked_dict[word];
          matches.push({
            pattern: 'dictionary',
            i: i,
            j: j,
            token: password.slice(i, +j + 1 || 9e9),
            matched_word: word,
            rank: rank,
            dictionary_name: dictionary_name,
            reversed: false,
            l33t: false
          });
        }
      }
    }
  }
  return this.sorted(matches);
}
```
- example usage
```shell
...
},
reverse_dictionary_match: function(password, _ranked_dictionaries) {
  var len1, match, matches, o, ref, reversed_password;
  if (_ranked_dictionaries == null) {
    _ranked_dictionaries = RANKED_DICTIONARIES;
  }
  reversed_password = password.split('').reverse().join('');
  matches = this.dictionary_match(reversed_password, _ranked_dictionaries);
  for (o = 0, len1 = matches.length; o < len1; o++) {
    match = matches[o];
    match.token = match.token.split('').reverse().join('');
    match.reversed = true;
    ref = [password.length - 1 - match.j, password.length - 1 - match.i], match.i = ref[0], match.j = ref[1];
  }
  return this.sorted(matches);
...
```

#### <a name="apidoc.element.zxcvbn.matching.empty"></a>[function <span class="apidocSignatureSpan">zxcvbn.matching.</span>empty (obj)](#apidoc.element.zxcvbn.matching.empty)
- description and source-code
```javascript
empty = function (obj) {
  var k;
  return ((function() {
    var results;
    results = [];
    for (k in obj) {
      results.push(k);
    }
    return results;
  })()).length === 0;
}
```
- example usage
```shell
...
if (_l33t_table == null) {
  _l33t_table = L33T_TABLE;
}
matches = [];
ref = this.enumerate_l33t_subs(this.relevant_l33t_subtable(password, _l33t_table));
for (o = 0, len1 = ref.length; o < len1; o++) {
  sub = ref[o];
  if (this.empty(sub)) {
    break;
  }
  subbed_password = this.translate(password, sub);
  ref1 = this.dictionary_match(subbed_password, _ranked_dictionaries);
  for (p = 0, len2 = ref1.length; p < len2; p++) {
    match = ref1[p];
    token = password.slice(match.i, +match.j + 1 || 9e9);
...
```

#### <a name="apidoc.element.zxcvbn.matching.enumerate_l33t_subs"></a>[function <span class="apidocSignatureSpan">zxcvbn.matching.</span>enumerate_l33t_subs (table)](#apidoc.element.zxcvbn.matching.enumerate_l33t_subs)
- description and source-code
```javascript
enumerate_l33t_subs = function (table) {
  var chr, dedup, helper, k, keys, l33t_chr, len1, len2, o, p, ref, sub, sub_dict, sub_dicts, subs;
  keys = (function() {
    var results;
    results = [];
    for (k in table) {
      results.push(k);
    }
    return results;
  })();
  subs = [[]];
  dedup = function(subs) {
    var assoc, deduped, label, len1, members, o, sub, v;
    deduped = [];
    members = {};
    for (o = 0, len1 = subs.length; o < len1; o++) {
      sub = subs[o];
      assoc = (function() {
        var len2, p, results;
        results = [];
        for (v = p = 0, len2 = sub.length; p < len2; v = ++p) {
          k = sub[v];
          results.push([k, v]);
        }
        return results;
      })();
      assoc.sort();
      label = ((function() {
        var len2, p, results;
        results = [];
        for (v = p = 0, len2 = assoc.length; p < len2; v = ++p) {
          k = assoc[v];
          results.push(k + ',' + v);
        }
        return results;
      })()).join('-');
      if (!(label in members)) {
        members[label] = true;
        deduped.push(sub);
      }
    }
    return deduped;
  };
  helper = function(keys) {
    var dup_l33t_index, first_key, i, l33t_chr, len1, len2, next_subs, o, p, q, ref, ref1, rest_keys, sub, sub_alternative, sub_extension
;
    if (!keys.length) {
      return;
    }
    first_key = keys[0];
    rest_keys = keys.slice(1);
    next_subs = [];
    ref = table[first_key];
    for (o = 0, len1 = ref.length; o < len1; o++) {
      l33t_chr = ref[o];
      for (p = 0, len2 = subs.length; p < len2; p++) {
        sub = subs[p];
        dup_l33t_index = -1;
        for (i = q = 0, ref1 = sub.length; 0 <= ref1 ? q < ref1 : q > ref1; i = 0 <= ref1 ? ++q : --q) {
          if (sub[i][0] === l33t_chr) {
            dup_l33t_index = i;
            break;
          }
        }
        if (dup_l33t_index === -1) {
          sub_extension = sub.concat([[l33t_chr, first_key]]);
          next_subs.push(sub_extension);
        } else {
          sub_alternative = sub.slice(0);
          sub_alternative.splice(dup_l33t_index, 1);
          sub_alternative.push([l33t_chr, first_key]);
          next_subs.push(sub);
          next_subs.push(sub_alternative);
        }
      }
    }
    subs = dedup(next_subs);
    return helper(rest_keys);
  };
  helper(keys);
  sub_dicts = [];
  for (o = 0, len1 = subs.length; o < len1; o++) {
    sub = subs[o];
    sub_dict = {};
    for (p = 0, len2 = sub.length; p < len2; p++) {
      ref = sub[p], l33t_chr = ref[0], chr = ref[1];
      sub_dict[l33t_chr] = chr;
    }
    sub_dicts.push(sub_dict);
  }
  return sub_dicts;
}
```
- example usage
```shell
...
if (_ranked_dictionaries == null) {
  _ranked_dictionaries = RANKED_DICTIONARIES;
}
if (_l33t_table == null) {
  _l33t_table = L33T_TABLE;
}
matches = [];
ref = this.enumerate_l33t_subs(this.relevant_l33t_subtable(password, _l33t_table));
for (o = 0, len1 = ref.length; o < len1; o++) {
  sub = ref[o];
  if (this.empty(sub)) {
    break;
  }
  subbed_password = this.translate(password, sub);
  ref1 = this.dictionary_match(subbed_password, _ranked_dictionaries);
...
```

#### <a name="apidoc.element.zxcvbn.matching.extend"></a>[function <span class="apidocSignatureSpan">zxcvbn.matching.</span>extend (lst, lst2)](#apidoc.element.zxcvbn.matching.extend)
- description and source-code
```javascript
extend = function (lst, lst2) {
  return lst.push.apply(lst, lst2);
}
```
- example usage
```shell
...
},
omnimatch: function(password) {
  var len1, matcher, matchers, matches, o;
  matches = [];
  matchers = [this.dictionary_match, this.reverse_dictionary_match, this.l33t_match, this.spatial_match, this.repeat_match, this
.sequence_match, this.regex_match, this.date_match];
  for (o = 0, len1 = matchers.length; o < len1; o++) {
    matcher = matchers[o];
    this.extend(matches, matcher.call(this, password));
  }
  return this.sorted(matches);
},
dictionary_match: function(password, _ranked_dictionaries) {
  var dictionary_name, i, j, len, matches, o, p, password_lower, rank, ranked_dict, ref, ref1, ref2, word;
  if (_ranked_dictionaries == null) {
    _ranked_dictionaries = RANKED_DICTIONARIES;
...
```

#### <a name="apidoc.element.zxcvbn.matching.l33t_match"></a>[function <span class="apidocSignatureSpan">zxcvbn.matching.</span>l33t_match (password, _ranked_dictionaries, _l33t_table)](#apidoc.element.zxcvbn.matching.l33t_match)
- description and source-code
```javascript
l33t_match = function (password, _ranked_dictionaries, _l33t_table) {
  var chr, k, len1, len2, match, match_sub, matches, o, p, ref, ref1, sub, subbed_chr, subbed_password, token, v;
  if (_ranked_dictionaries == null) {
    _ranked_dictionaries = RANKED_DICTIONARIES;
  }
  if (_l33t_table == null) {
    _l33t_table = L33T_TABLE;
  }
  matches = [];
  ref = this.enumerate_l33t_subs(this.relevant_l33t_subtable(password, _l33t_table));
  for (o = 0, len1 = ref.length; o < len1; o++) {
    sub = ref[o];
    if (this.empty(sub)) {
      break;
    }
    subbed_password = this.translate(password, sub);
    ref1 = this.dictionary_match(subbed_password, _ranked_dictionaries);
    for (p = 0, len2 = ref1.length; p < len2; p++) {
      match = ref1[p];
      token = password.slice(match.i, +match.j + 1 || 9e9);
      if (token.toLowerCase() === match.matched_word) {
        continue;
      }
      match_sub = {};
      for (subbed_chr in sub) {
        chr = sub[subbed_chr];
        if (token.indexOf(subbed_chr) !== -1) {
          match_sub[subbed_chr] = chr;
        }
      }
      match.l33t = true;
      match.token = token;
      match.sub = match_sub;
      match.sub_display = ((function() {
        var results;
        results = [];
        for (k in match_sub) {
          v = match_sub[k];
          results.push(k + " -> " + v);
        }
        return results;
      })()).join(', ');
      matches.push(match);
    }
  }
  return this.sorted(matches.filter(function(match) {
    return match.token.length > 1;
  }));
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.zxcvbn.matching.map_ints_to_dm"></a>[function <span class="apidocSignatureSpan">zxcvbn.matching.</span>map_ints_to_dm (ints)](#apidoc.element.zxcvbn.matching.map_ints_to_dm)
- description and source-code
```javascript
map_ints_to_dm = function (ints) {
  var d, len1, m, o, ref, ref1;
  ref = [ints, ints.slice().reverse()];
  for (o = 0, len1 = ref.length; o < len1; o++) {
    ref1 = ref[o], d = ref1[0], m = ref1[1];
    if ((1 <= d && d <= 31) && (1 <= m && m <= 12)) {
      return {
        day: d,
        month: m
      };
    }
  }
}
```
- example usage
```shell
...
if (over_31 >= 2 || over_12 === 3 || under_1 >= 2) {
  return;
}
possible_year_splits = [[ints[2], ints.slice(0, 2)], [ints[0], ints.slice(1, 3)]];
for (p = 0, len2 = possible_year_splits.length; p < len2; p++) {
  ref = possible_year_splits[p], y = ref[0], rest = ref[1];
  if ((DATE_MIN_YEAR <= y && y <= DATE_MAX_YEAR)) {
    dm = this.map_ints_to_dm(rest);
    if (dm != null) {
      return {
        year: y,
        month: dm.month,
        day: dm.day
      };
    } else {
...
```

#### <a name="apidoc.element.zxcvbn.matching.map_ints_to_dmy"></a>[function <span class="apidocSignatureSpan">zxcvbn.matching.</span>map_ints_to_dmy (ints)](#apidoc.element.zxcvbn.matching.map_ints_to_dmy)
- description and source-code
```javascript
map_ints_to_dmy = function (ints) {
  var dm, int, len1, len2, len3, o, over_12, over_31, p, possible_year_splits, q, ref, ref1, rest, under_1, y;
  if (ints[1] > 31 || ints[1] <= 0) {
    return;
  }
  over_12 = 0;
  over_31 = 0;
  under_1 = 0;
  for (o = 0, len1 = ints.length; o < len1; o++) {
    int = ints[o];
    if ((99 < int && int < DATE_MIN_YEAR) || int > DATE_MAX_YEAR) {
      return;
    }
    if (int > 31) {
      over_31 += 1;
    }
    if (int > 12) {
      over_12 += 1;
    }
    if (int <= 0) {
      under_1 += 1;
    }
  }
  if (over_31 >= 2 || over_12 === 3 || under_1 >= 2) {
    return;
  }
  possible_year_splits = [[ints[2], ints.slice(0, 2)], [ints[0], ints.slice(1, 3)]];
  for (p = 0, len2 = possible_year_splits.length; p < len2; p++) {
    ref = possible_year_splits[p], y = ref[0], rest = ref[1];
    if ((DATE_MIN_YEAR <= y && y <= DATE_MAX_YEAR)) {
      dm = this.map_ints_to_dm(rest);
      if (dm != null) {
        return {
          year: y,
          month: dm.month,
          day: dm.day
        };
      } else {
        return;
      }
    }
  }
  for (q = 0, len3 = possible_year_splits.length; q < len3; q++) {
    ref1 = possible_year_splits[q], y = ref1[0], rest = ref1[1];
    dm = this.map_ints_to_dm(rest);
    if (dm != null) {
      y = this.two_to_four_digit_year(y);
      return {
        year: y,
        month: dm.month,
        day: dm.day
      };
    }
  }
}
```
- example usage
```shell
...
if (!maybe_date_no_separator.exec(token)) {
  continue;
}
candidates = [];
ref3 = DATE_SPLITS[token.length];
for (q = 0, len1 = ref3.length; q < len1; q++) {
  ref4 = ref3[q], k = ref4[0], l = ref4[1];
  dmy = this.map_ints_to_dmy([parseInt(token.slice(0, k)), parseInt(token.slice(k, l)), parseInt(token.slice(l))]);
  if (dmy != null) {
    candidates.push(dmy);
  }
}
if (!(candidates.length > 0)) {
  continue;
}
...
```

#### <a name="apidoc.element.zxcvbn.matching.mod"></a>[function <span class="apidocSignatureSpan">zxcvbn.matching.</span>mod (n, m)](#apidoc.element.zxcvbn.matching.mod)
- description and source-code
```javascript
mod = function (n, m) {
  return ((n % m) + m) % m;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.zxcvbn.matching.omnimatch"></a>[function <span class="apidocSignatureSpan">zxcvbn.matching.</span>omnimatch (password)](#apidoc.element.zxcvbn.matching.omnimatch)
- description and source-code
```javascript
omnimatch = function (password) {
  var len1, matcher, matchers, matches, o;
  matches = [];
  matchers = [this.dictionary_match, this.reverse_dictionary_match, this.l33t_match, this.spatial_match, this.repeat_match, this
.sequence_match, this.regex_match, this.date_match];
  for (o = 0, len1 = matchers.length; o < len1; o++) {
    matcher = matchers[o];
    this.extend(matches, matcher.call(this, password));
  }
  return this.sorted(matches);
}
```
- example usage
```shell
...
  match = greedy_match;
  base_token = lazy_anchored.exec(match[0])[1];
} else {
  match = lazy_match;
  base_token = match[1];
}
ref = [match.index, match.index + match[0].length - 1], i = ref[0], j = ref[1];
base_analysis = scoring.most_guessable_match_sequence(base_token, this.omnimatch(base_token));
base_matches = base_analysis.sequence;
base_guesses = base_analysis.guesses;
matches.push({
  pattern: 'repeat',
  i: i,
  j: j,
  token: match[0],
...
```

#### <a name="apidoc.element.zxcvbn.matching.regex_match"></a>[function <span class="apidocSignatureSpan">zxcvbn.matching.</span>regex_match (password, _regexen)](#apidoc.element.zxcvbn.matching.regex_match)
- description and source-code
```javascript
regex_match = function (password, _regexen) {
  var matches, regex, rx_match, token;
  if (_regexen == null) {
    _regexen = REGEXEN;
  }
  matches = [];
  for (name in _regexen) {
    regex = _regexen[name];
    regex.lastIndex = 0;
    while (rx_match = regex.exec(password)) {
      token = rx_match[0];
      matches.push({
        pattern: 'regex',
        token: token,
        i: rx_match.index,
        j: rx_match.index + rx_match[0].length - 1,
        regex_name: name,
        regex_match: rx_match
      });
    }
  }
  return this.sorted(matches);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.zxcvbn.matching.relevant_l33t_subtable"></a>[function <span class="apidocSignatureSpan">zxcvbn.matching.</span>relevant_l33t_subtable (password, table)](#apidoc.element.zxcvbn.matching.relevant_l33t_subtable)
- description and source-code
```javascript
relevant_l33t_subtable = function (password, table) {
  var chr, len1, letter, o, password_chars, ref, relevant_subs, sub, subs, subtable;
  password_chars = {};
  ref = password.split('');
  for (o = 0, len1 = ref.length; o < len1; o++) {
    chr = ref[o];
    password_chars[chr] = true;
  }
  subtable = {};
  for (letter in table) {
    subs = table[letter];
    relevant_subs = (function() {
      var len2, p, results;
      results = [];
      for (p = 0, len2 = subs.length; p < len2; p++) {
        sub = subs[p];
        if (sub in password_chars) {
          results.push(sub);
        }
      }
      return results;
    })();
    if (relevant_subs.length > 0) {
      subtable[letter] = relevant_subs;
    }
  }
  return subtable;
}
```
- example usage
```shell
...
if (_ranked_dictionaries == null) {
  _ranked_dictionaries = RANKED_DICTIONARIES;
}
if (_l33t_table == null) {
  _l33t_table = L33T_TABLE;
}
matches = [];
ref = this.enumerate_l33t_subs(this.relevant_l33t_subtable(password, _l33t_table));
for (o = 0, len1 = ref.length; o < len1; o++) {
  sub = ref[o];
  if (this.empty(sub)) {
    break;
  }
  subbed_password = this.translate(password, sub);
  ref1 = this.dictionary_match(subbed_password, _ranked_dictionaries);
...
```

#### <a name="apidoc.element.zxcvbn.matching.repeat_match"></a>[function <span class="apidocSignatureSpan">zxcvbn.matching.</span>repeat_match (password)](#apidoc.element.zxcvbn.matching.repeat_match)
- description and source-code
```javascript
repeat_match = function (password) {
  var base_analysis, base_guesses, base_matches, base_token, greedy, greedy_match, i, j, lastIndex, lazy, lazy_anchored, lazy_match
, match, matches, ref;
  matches = [];
  greedy = /(.+)\1+/g;
  lazy = /(.+?)\1+/g;
  lazy_anchored = /^(.+?)\1+$/;
  lastIndex = 0;
  while (lastIndex < password.length) {
    greedy.lastIndex = lazy.lastIndex = lastIndex;
    greedy_match = greedy.exec(password);
    lazy_match = lazy.exec(password);
    if (greedy_match == null) {
      break;
    }
    if (greedy_match[0].length > lazy_match[0].length) {
      match = greedy_match;
      base_token = lazy_anchored.exec(match[0])[1];
    } else {
      match = lazy_match;
      base_token = match[1];
    }
    ref = [match.index, match.index + match[0].length - 1], i = ref[0], j = ref[1];
    base_analysis = scoring.most_guessable_match_sequence(base_token, this.omnimatch(base_token));
    base_matches = base_analysis.sequence;
    base_guesses = base_analysis.guesses;
    matches.push({
      pattern: 'repeat',
      i: i,
      j: j,
      token: match[0],
      base_token: base_token,
      base_guesses: base_guesses,
      base_matches: base_matches,
      repeat_count: match[0].length / base_token.length
    });
    lastIndex = j + 1;
  }
  return matches;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.zxcvbn.matching.reverse_dictionary_match"></a>[function <span class="apidocSignatureSpan">zxcvbn.matching.</span>reverse_dictionary_match (password, _ranked_dictionaries)](#apidoc.element.zxcvbn.matching.reverse_dictionary_match)
- description and source-code
```javascript
reverse_dictionary_match = function (password, _ranked_dictionaries) {
  var len1, match, matches, o, ref, reversed_password;
  if (_ranked_dictionaries == null) {
    _ranked_dictionaries = RANKED_DICTIONARIES;
  }
  reversed_password = password.split('').reverse().join('');
  matches = this.dictionary_match(reversed_password, _ranked_dictionaries);
  for (o = 0, len1 = matches.length; o < len1; o++) {
    match = matches[o];
    match.token = match.token.split('').reverse().join('');
    match.reversed = true;
    ref = [password.length - 1 - match.j, password.length - 1 - match.i], match.i = ref[0], match.j = ref[1];
  }
  return this.sorted(matches);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.zxcvbn.matching.sequence_match"></a>[function <span class="apidocSignatureSpan">zxcvbn.matching.</span>sequence_match (password)](#apidoc.element.zxcvbn.matching.sequence_match)
- description and source-code
```javascript
sequence_match = function (password) {
  var delta, i, j, k, last_delta, o, ref, result, update;
  if (password.length === 1) {
    return [];
  }
  update = (function(_this) {
    return function(i, j, delta) {
      var ref, sequence_name, sequence_space, token;
      if (j - i > 1 || Math.abs(delta) === 1) {
        if ((0 < (ref = Math.abs(delta)) && ref <= _this.MAX_DELTA)) {
          token = password.slice(i, +j + 1 || 9e9);
          if (/^[a-z]+$/.test(token)) {
            sequence_name = 'lower';
            sequence_space = 26;
          } else if (/^[A-Z]+$/.test(token)) {
            sequence_name = 'upper';
            sequence_space = 26;
          } else if (/^\d+$/.test(token)) {
            sequence_name = 'digits';
            sequence_space = 10;
          } else {
            sequence_name = 'unicode';
            sequence_space = 26;
          }
          return result.push({
            pattern: 'sequence',
            i: i,
            j: j,
            token: password.slice(i, +j + 1 || 9e9),
            sequence_name: sequence_name,
            sequence_space: sequence_space,
            ascending: delta > 0
          });
        }
      }
    };
  })(this);
  result = [];
  i = 0;
  last_delta = null;
  for (k = o = 1, ref = password.length; 1 <= ref ? o < ref : o > ref; k = 1 <= ref ? ++o : --o) {
    delta = password.charCodeAt(k) - password.charCodeAt(k - 1);
    if (last_delta == null) {
      last_delta = delta;
    }
    if (delta === last_delta) {
      continue;
    }
    j = k - 1;
    update(i, j, last_delta);
    i = j;
    last_delta = delta;
  }
  update(i, password.length - 1, last_delta);
  return result;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.zxcvbn.matching.set_user_input_dictionary"></a>[function <span class="apidocSignatureSpan">zxcvbn.matching.</span>set_user_input_dictionary (ordered_list)](#apidoc.element.zxcvbn.matching.set_user_input_dictionary)
- description and source-code
```javascript
set_user_input_dictionary = function (ordered_list) {
  return RANKED_DICTIONARIES['user_inputs'] = build_ranked_dict(ordered_list.slice());
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.zxcvbn.matching.sorted"></a>[function <span class="apidocSignatureSpan">zxcvbn.matching.</span>sorted (matches)](#apidoc.element.zxcvbn.matching.sorted)
- description and source-code
```javascript
sorted = function (matches) {
  return matches.sort(function(m1, m2) {
    return (m1.i - m2.i) || (m1.j - m2.j);
  });
}
```
- example usage
```shell
...
  var len1, matcher, matchers, matches, o;
  matches = [];
  matchers = [this.dictionary_match, this.reverse_dictionary_match, this.l33t_match, this.spatial_match, this.repeat_match, this
.sequence_match, this.regex_match, this.date_match];
  for (o = 0, len1 = matchers.length; o < len1; o++) {
    matcher = matchers[o];
    this.extend(matches, matcher.call(this, password));
  }
  return this.sorted(matches);
},
dictionary_match: function(password, _ranked_dictionaries) {
  var dictionary_name, i, j, len, matches, o, p, password_lower, rank, ranked_dict, ref, ref1, ref2, word;
  if (_ranked_dictionaries == null) {
    _ranked_dictionaries = RANKED_DICTIONARIES;
  }
  matches = [];
...
```

#### <a name="apidoc.element.zxcvbn.matching.spatial_match"></a>[function <span class="apidocSignatureSpan">zxcvbn.matching.</span>spatial_match (password, _graphs)](#apidoc.element.zxcvbn.matching.spatial_match)
- description and source-code
```javascript
spatial_match = function (password, _graphs) {
  var graph, graph_name, matches;
  if (_graphs == null) {
    _graphs = GRAPHS;
  }
  matches = [];
  for (graph_name in _graphs) {
    graph = _graphs[graph_name];
    this.extend(matches, this.spatial_match_helper(password, graph, graph_name));
  }
  return this.sorted(matches);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.zxcvbn.matching.spatial_match_helper"></a>[function <span class="apidocSignatureSpan">zxcvbn.matching.</span>spatial_match_helper (password, graph, graph_name)](#apidoc.element.zxcvbn.matching.spatial_match_helper)
- description and source-code
```javascript
spatial_match_helper = function (password, graph, graph_name) {
  var adj, adjacents, cur_char, cur_direction, found, found_direction, i, j, last_direction, len1, matches, o, prev_char, shifted_count
, turns;
  matches = [];
  i = 0;
  while (i < password.length - 1) {
    j = i + 1;
    last_direction = null;
    turns = 0;
    if ((graph_name === 'qwerty' || graph_name === 'dvorak') && this.SHIFTED_RX.exec(password.charAt(i))) {
      shifted_count = 1;
    } else {
      shifted_count = 0;
    }
    while (true) {
      prev_char = password.charAt(j - 1);
      found = false;
      found_direction = -1;
      cur_direction = -1;
      adjacents = graph[prev_char] || [];
      if (j < password.length) {
        cur_char = password.charAt(j);
        for (o = 0, len1 = adjacents.length; o < len1; o++) {
          adj = adjacents[o];
          cur_direction += 1;
          if (adj && adj.indexOf(cur_char) !== -1) {
            found = true;
            found_direction = cur_direction;
            if (adj.indexOf(cur_char) === 1) {
              shifted_count += 1;
            }
            if (last_direction !== found_direction) {
              turns += 1;
              last_direction = found_direction;
            }
            break;
          }
        }
      }
      if (found) {
        j += 1;
      } else {
        if (j - i > 2) {
          matches.push({
            pattern: 'spatial',
            i: i,
            j: j - 1,
            token: password.slice(i, j),
            graph: graph_name,
            turns: turns,
            shifted_count: shifted_count
          });
        }
        i = j;
        break;
      }
    }
  }
  return matches;
}
```
- example usage
```shell
...
  var graph, graph_name, matches;
  if (_graphs == null) {
    _graphs = GRAPHS;
  }
  matches = [];
  for (graph_name in _graphs) {
    graph = _graphs[graph_name];
    this.extend(matches, this.spatial_match_helper(password, graph, graph_name));
  }
  return this.sorted(matches);
},
SHIFTED_RX: /[~!@#$%^&*()_+QWERTYUIOP{}|ASDFGHJKL:"ZXCVBNM<>?]/,
spatial_match_helper: function(password, graph, graph_name) {
  var adj, adjacents, cur_char, cur_direction, found, found_direction, i, j, last_direction, len1, matches, o, prev_char, shifted_count
, turns;
  matches = [];
...
```

#### <a name="apidoc.element.zxcvbn.matching.translate"></a>[function <span class="apidocSignatureSpan">zxcvbn.matching.</span>translate (string, chr_map)](#apidoc.element.zxcvbn.matching.translate)
- description and source-code
```javascript
translate = function (string, chr_map) {
  var chr;
  return ((function() {
    var len1, o, ref, results;
    ref = string.split('');
    results = [];
    for (o = 0, len1 = ref.length; o < len1; o++) {
      chr = ref[o];
      results.push(chr_map[chr] || chr);
    }
    return results;
  })()).join('');
}
```
- example usage
```shell
...
matches = [];
ref = this.enumerate_l33t_subs(this.relevant_l33t_subtable(password, _l33t_table));
for (o = 0, len1 = ref.length; o < len1; o++) {
  sub = ref[o];
  if (this.empty(sub)) {
    break;
  }
  subbed_password = this.translate(password, sub);
  ref1 = this.dictionary_match(subbed_password, _ranked_dictionaries);
  for (p = 0, len2 = ref1.length; p < len2; p++) {
    match = ref1[p];
    token = password.slice(match.i, +match.j + 1 || 9e9);
    if (token.toLowerCase() === match.matched_word) {
      continue;
    }
...
```

#### <a name="apidoc.element.zxcvbn.matching.two_to_four_digit_year"></a>[function <span class="apidocSignatureSpan">zxcvbn.matching.</span>two_to_four_digit_year (year)](#apidoc.element.zxcvbn.matching.two_to_four_digit_year)
- description and source-code
```javascript
two_to_four_digit_year = function (year) {
  if (year > 99) {
    return year;
  } else if (year > 50) {
    return year + 1900;
  } else {
    return year + 2000;
  }
}
```
- example usage
```shell
...
    }
  }
}
for (q = 0, len3 = possible_year_splits.length; q < len3; q++) {
  ref1 = possible_year_splits[q], y = ref1[0], rest = ref1[1];
  dm = this.map_ints_to_dm(rest);
  if (dm != null) {
    y = this.two_to_four_digit_year(y);
    return {
      year: y,
      month: dm.month,
      day: dm.day
    };
  }
}
...
```



# <a name="apidoc.module.zxcvbn.scoring"></a>[module zxcvbn.scoring](#apidoc.module.zxcvbn.scoring)

#### <a name="apidoc.element.zxcvbn.scoring.bruteforce_guesses"></a>[function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>bruteforce_guesses (match)](#apidoc.element.zxcvbn.scoring.bruteforce_guesses)
- description and source-code
```javascript
bruteforce_guesses = function (match) {
  var guesses, min_guesses;
  guesses = Math.pow(BRUTEFORCE_CARDINALITY, match.token.length);
  if (guesses === Number.POSITIVE_INFINITY) {
    guesses = Number.MAX_VALUE;
  }
  min_guesses = match.token.length === 1 ? MIN_SUBMATCH_GUESSES_SINGLE_CHAR + 1 : MIN_SUBMATCH_GUESSES_MULTI_CHAR + 1;
  return Math.max(guesses, min_guesses);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.zxcvbn.scoring.date_guesses"></a>[function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>date_guesses (match)](#apidoc.element.zxcvbn.scoring.date_guesses)
- description and source-code
```javascript
date_guesses = function (match) {
  var guesses, year_space;
  year_space = Math.max(Math.abs(match.year - this.REFERENCE_YEAR), this.MIN_YEAR_SPACE);
  guesses = year_space * 365;
  if (match.separator) {
    guesses *= 4;
  }
  return guesses;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.zxcvbn.scoring.dictionary_guesses"></a>[function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>dictionary_guesses (match)](#apidoc.element.zxcvbn.scoring.dictionary_guesses)
- description and source-code
```javascript
dictionary_guesses = function (match) {
  var reversed_variations;
  match.base_guesses = match.rank;
  match.uppercase_variations = this.uppercase_variations(match);
  match.l33t_variations = this.l33t_variations(match);
  reversed_variations = match.reversed && 2 || 1;
  return match.base_guesses * match.uppercase_variations * match.l33t_variations * reversed_variations;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.zxcvbn.scoring.estimate_guesses"></a>[function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>estimate_guesses (match, password)](#apidoc.element.zxcvbn.scoring.estimate_guesses)
- description and source-code
```javascript
estimate_guesses = function (match, password) {
  var estimation_functions, guesses, min_guesses;
  if (match.guesses != null) {
    return match.guesses;
  }
  min_guesses = 1;
  if (match.token.length < password.length) {
    min_guesses = match.token.length === 1 ? MIN_SUBMATCH_GUESSES_SINGLE_CHAR : MIN_SUBMATCH_GUESSES_MULTI_CHAR;
  }
  estimation_functions = {
    bruteforce: this.bruteforce_guesses,
    dictionary: this.dictionary_guesses,
    spatial: this.spatial_guesses,
    repeat: this.repeat_guesses,
    sequence: this.sequence_guesses,
    regex: this.regex_guesses,
    date: this.date_guesses
  };
  guesses = estimation_functions[match.pattern].call(this, match);
  match.guesses = Math.max(guesses, min_guesses);
  match.guesses_log10 = this.log10(match.guesses);
  return match.guesses;
}
```
- example usage
```shell
...
    return results;
  })()
};
update = (function(_this) {
  return function(m, l) {
    var competing_g, competing_l, g, k, pi, ref;
    k = m.j;
    pi = _this.estimate_guesses(m, password);
    if (l > 1) {
      pi *= optimal.pi[m.i - 1][l - 1];
    }
    g = _this.factorial(l) * pi;
    if (!_exclude_additive) {
      g += Math.pow(MIN_GUESSES_BEFORE_GROWING_SEQUENCE, l - 1);
    }
...
```

#### <a name="apidoc.element.zxcvbn.scoring.factorial"></a>[function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>factorial (n)](#apidoc.element.zxcvbn.scoring.factorial)
- description and source-code
```javascript
factorial = function (n) {
  var f, i, o, ref;
  if (n < 2) {
    return 1;
  }
  f = 1;
  for (i = o = 2, ref = n; 2 <= ref ? o <= ref : o >= ref; i = 2 <= ref ? ++o : --o) {
    f *= i;
  }
  return f;
}
```
- example usage
```shell
...
      return function(m, l) {
var competing_g, competing_l, g, k, pi, ref;
k = m.j;
pi = _this.estimate_guesses(m, password);
if (l > 1) {
  pi *= optimal.pi[m.i - 1][l - 1];
}
g = _this.factorial(l) * pi;
if (!_exclude_additive) {
  g += Math.pow(MIN_GUESSES_BEFORE_GROWING_SEQUENCE, l - 1);
}
ref = optimal.g[k];
for (competing_l in ref) {
  competing_g = ref[competing_l];
  if (competing_l > l) {
...
```

#### <a name="apidoc.element.zxcvbn.scoring.l33t_variations"></a>[function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>l33t_variations (match)](#apidoc.element.zxcvbn.scoring.l33t_variations)
- description and source-code
```javascript
l33t_variations = function (match) {
  var S, U, chr, chrs, i, o, p, possibilities, ref, ref1, subbed, unsubbed, variations;
  if (!match.l33t) {
    return 1;
  }
  variations = 1;
  ref = match.sub;
  for (subbed in ref) {
    unsubbed = ref[subbed];
    chrs = match.token.toLowerCase().split('');
    S = ((function() {
      var len, o, results;
      results = [];
      for (o = 0, len = chrs.length; o < len; o++) {
        chr = chrs[o];
        if (chr === subbed) {
          results.push(chr);
        }
      }
      return results;
    })()).length;
    U = ((function() {
      var len, o, results;
      results = [];
      for (o = 0, len = chrs.length; o < len; o++) {
        chr = chrs[o];
        if (chr === unsubbed) {
          results.push(chr);
        }
      }
      return results;
    })()).length;
    if (S === 0 || U === 0) {
      variations *= 2;
    } else {
      p = Math.min(U, S);
      possibilities = 0;
      for (i = o = 1, ref1 = p; 1 <= ref1 ? o <= ref1 : o >= ref1; i = 1 <= ref1 ? ++o : --o) {
        possibilities += this.nCk(U + S, i);
      }
      variations *= possibilities;
    }
  }
  return variations;
}
```
- example usage
```shell
...
  }
  return guesses;
},
dictionary_guesses: function(match) {
  var reversed_variations;
  match.base_guesses = match.rank;
  match.uppercase_variations = this.uppercase_variations(match);
  match.l33t_variations = this.l33t_variations(match);
  reversed_variations = match.reversed && 2 || 1;
  return match.base_guesses * match.uppercase_variations * match.l33t_variations * reversed_variations;
},
START_UPPER: /^[A-Z][^A-Z]+$/,
END_UPPER: /^[^A-Z]+[A-Z]$/,
ALL_UPPER: /^[^a-z]+$/,
ALL_LOWER: /^[^A-Z]+$/,
...
```

#### <a name="apidoc.element.zxcvbn.scoring.log10"></a>[function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>log10 (n)](#apidoc.element.zxcvbn.scoring.log10)
- description and source-code
```javascript
log10 = function (n) {
  return Math.log(n) / Math.log(10);
}
```
- example usage
```shell
...
    guesses = 1;
  } else {
    guesses = optimal.g[n - 1][optimal_l];
  }
  return {
    password: password,
    guesses: guesses,
    guesses_log10: this.log10(guesses),
    sequence: optimal_match_sequence
  };
},
estimate_guesses: function(match, password) {
  var estimation_functions, guesses, min_guesses;
  if (match.guesses != null) {
    return match.guesses;
...
```

#### <a name="apidoc.element.zxcvbn.scoring.log2"></a>[function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>log2 (n)](#apidoc.element.zxcvbn.scoring.log2)
- description and source-code
```javascript
log2 = function (n) {
  return Math.log(n) / Math.log(2);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.zxcvbn.scoring.most_guessable_match_sequence"></a>[function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>most_guessable_match_sequence (password, matches, _exclude_additive)](#apidoc.element.zxcvbn.scoring.most_guessable_match_sequence)
- description and source-code
```javascript
most_guessable_match_sequence = function (password, matches, _exclude_additive) {
  var _, bruteforce_update, guesses, k, l, len, len1, len2, lst, m, make_bruteforce_match, matches_by_j, n, o, optimal, optimal_l
, optimal_match_sequence, q, ref, ref1, u, unwind, update, w;
  if (_exclude_additive == null) {
    _exclude_additive = false;
  }
  n = password.length;
  matches_by_j = (function() {
    var o, ref, results;
    results = [];
    for (_ = o = 0, ref = n; 0 <= ref ? o < ref : o > ref; _ = 0 <= ref ? ++o : --o) {
      results.push([]);
    }
    return results;
  })();
  for (o = 0, len = matches.length; o < len; o++) {
    m = matches[o];
    matches_by_j[m.j].push(m);
  }
  for (q = 0, len1 = matches_by_j.length; q < len1; q++) {
    lst = matches_by_j[q];
    lst.sort(function(m1, m2) {
      return m1.i - m2.i;
    });
  }
  optimal = {
    m: (function() {
      var ref, results, u;
      results = [];
      for (_ = u = 0, ref = n; 0 <= ref ? u < ref : u > ref; _ = 0 <= ref ? ++u : --u) {
        results.push({});
      }
      return results;
    })(),
    pi: (function() {
      var ref, results, u;
      results = [];
      for (_ = u = 0, ref = n; 0 <= ref ? u < ref : u > ref; _ = 0 <= ref ? ++u : --u) {
        results.push({});
      }
      return results;
    })(),
    g: (function() {
      var ref, results, u;
      results = [];
      for (_ = u = 0, ref = n; 0 <= ref ? u < ref : u > ref; _ = 0 <= ref ? ++u : --u) {
        results.push({});
      }
      return results;
    })()
  };
  update = (function(_this) {
    return function(m, l) {
      var competing_g, competing_l, g, k, pi, ref;
      k = m.j;
      pi = _this.estimate_guesses(m, password);
      if (l > 1) {
        pi *= optimal.pi[m.i - 1][l - 1];
      }
      g = _this.factorial(l) * pi;
      if (!_exclude_additive) {
        g += Math.pow(MIN_GUESSES_BEFORE_GROWING_SEQUENCE, l - 1);
      }
      ref = optimal.g[k];
      for (competing_l in ref) {
        competing_g = ref[competing_l];
        if (competing_l > l) {
          continue;
        }
        if (competing_g <= g) {
          return;
        }
      }
      optimal.g[k][l] = g;
      optimal.m[k][l] = m;
      return optimal.pi[k][l] = pi;
    };
  })(this);
  bruteforce_update = (function(_this) {
    return function(k) {
      var i, l, last_m, ref, results, u;
      m = make_bruteforce_match(0, k);
      update(m, 1);
      results = [];
      for (i = u = 1, ref = k; 1 <= ref ? u <= ref : u >= ref; i = 1 <= ref ? ++u : --u) {
        m = make_bruteforce_match(i, k);
        results.push((function() {
          var ref1, results1;
          ref1 = optimal.m[i - 1];
          results1 = [];
          for (l in ref1) {
            last_m = ref1[l];
            l = parseInt(l);
            if (last_m.pattern === 'bruteforce') {
              continue;
            }
            results1.push(update(m, l + 1));
          }
          return results1;
        })());
      }
      return results;
    };
  })(this);
  make_bruteforce_match = (function(_this) {
    return function(i, j) {
      return {
        pattern: 'bruteforce',
        token: password.slice(i, +j + 1 || 9e9),
        i: i,
        j: j
      };
    };
  })(this);
  unwind = (function(_this) {
    return function(n) {
      var candidate_g, candidate_l, g, k, l, optimal_match_sequence, ref;
      optimal_match_sequence = [];
      k = n - 1;
      l = void 0;
      g = Infinity;
      ref = optimal.g[k];
      for (candidate_l in ref) {
        candidate_g = ref[candidate_l];
        if (candidate_g < g) {
          l = candidate_l;
          g = candidate_g;
        }
      }
      while (k >= 0) {
        m = optimal.m[k][l];
        optimal_match_sequence.unshift(m);
        k = m.i - 1;
        l--;
      }
      return optimal_match_sequence;
    };
  })(this);
  for (k = u = 0, ref = n; 0 <= ref ? u < ref : u > ref; k = 0 <= ref ? ++u : --u) {
    ref1 = matches_by_j[k];
    for (w = 0, len2 = ref1.length; w < len2; w++) {
      m = ref1[w];
      if (m.i > 0) {
        for (l in optimal.m[m.i - 1]) {
          l = parseIn ...
```
- example usage
```shell
...
  match = greedy_match;
  base_token = lazy_anchored.exec(match[0])[1];
} else {
  match = lazy_match;
  base_token = match[1];
}
ref = [match.index, match.index + match[0].length - 1], i = ref[0], j = ref[1];
base_analysis = scoring.most_guessable_match_sequence(base_token, this.omnimatch(base_token));
base_matches = base_analysis.sequence;
base_guesses = base_analysis.guesses;
matches.push({
  pattern: 'repeat',
  i: i,
  j: j,
  token: match[0],
...
```

#### <a name="apidoc.element.zxcvbn.scoring.nCk"></a>[function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>nCk (n, k)](#apidoc.element.zxcvbn.scoring.nCk)
- description and source-code
```javascript
nCk = function (n, k) {
  var d, o, r, ref;
  if (k > n) {
    return 0;
  }
  if (k === 0) {
    return 1;
  }
  r = 1;
  for (d = o = 1, ref = k; 1 <= ref ? o <= ref : o >= ref; d = 1 <= ref ? ++o : --o) {
    r *= n;
    r /= d;
    n -= 1;
  }
  return r;
}
```
- example usage
```shell
...
}
guesses = 0;
L = match.token.length;
t = match.turns;
for (i = o = 2, ref1 = L; 2 <= ref1 ? o <= ref1 : o >= ref1; i = 2 <= ref1 ? ++o : --o) {
  possible_turns = Math.min(t, i - 1);
  for (j = q = 1, ref2 = possible_turns; 1 <= ref2 ? q <= ref2 : q >= ref2; j = 1 <= ref2 ? ++q : --q) {
    guesses += this.nCk(i - 1, j - 1) * s * Math.pow(d, j);
  }
}
if (match.shifted_count) {
  S = match.shifted_count;
  U = match.token.length - match.shifted_count;
  if (S === 0 || U === 0) {
    guesses *= 2;
...
```

#### <a name="apidoc.element.zxcvbn.scoring.regex_guesses"></a>[function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>regex_guesses (match)](#apidoc.element.zxcvbn.scoring.regex_guesses)
- description and source-code
```javascript
regex_guesses = function (match) {
  var char_class_bases, year_space;
  char_class_bases = {
    alpha_lower: 26,
    alpha_upper: 26,
    alpha: 52,
    alphanumeric: 62,
    digits: 10,
    symbols: 33
  };
  if (match.regex_name in char_class_bases) {
    return Math.pow(char_class_bases[match.regex_name], match.token.length);
  } else {
    switch (match.regex_name) {
      case 'recent_year':
        year_space = Math.abs(parseInt(match.regex_match[0]) - this.REFERENCE_YEAR);
        year_space = Math.max(year_space, this.MIN_YEAR_SPACE);
        return year_space;
    }
  }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.zxcvbn.scoring.repeat_guesses"></a>[function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>repeat_guesses (match)](#apidoc.element.zxcvbn.scoring.repeat_guesses)
- description and source-code
```javascript
repeat_guesses = function (match) {
  return match.base_guesses * match.repeat_count;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.zxcvbn.scoring.sequence_guesses"></a>[function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>sequence_guesses (match)](#apidoc.element.zxcvbn.scoring.sequence_guesses)
- description and source-code
```javascript
sequence_guesses = function (match) {
  var base_guesses, first_chr;
  first_chr = match.token.charAt(0);
  if (first_chr === 'a' || first_chr === 'A' || first_chr === 'z' || first_chr === 'Z' || first_chr === '0' || first_chr === '1' ||
first_chr === '9') {
    base_guesses = 4;
  } else {
    if (first_chr.match(/\d/)) {
      base_guesses = 10;
    } else {
      base_guesses = 26;
    }
  }
  if (!match.ascending) {
    base_guesses *= 2;
  }
  return base_guesses * match.token.length;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.zxcvbn.scoring.spatial_guesses"></a>[function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>spatial_guesses (match)](#apidoc.element.zxcvbn.scoring.spatial_guesses)
- description and source-code
```javascript
spatial_guesses = function (match) {
  var L, S, U, d, guesses, i, j, o, possible_turns, q, ref, ref1, ref2, ref3, s, shifted_variations, t, u;
  if ((ref = match.graph) === 'qwerty' || ref === 'dvorak') {
    s = this.KEYBOARD_STARTING_POSITIONS;
    d = this.KEYBOARD_AVERAGE_DEGREE;
  } else {
    s = this.KEYPAD_STARTING_POSITIONS;
    d = this.KEYPAD_AVERAGE_DEGREE;
  }
  guesses = 0;
  L = match.token.length;
  t = match.turns;
  for (i = o = 2, ref1 = L; 2 <= ref1 ? o <= ref1 : o >= ref1; i = 2 <= ref1 ? ++o : --o) {
    possible_turns = Math.min(t, i - 1);
    for (j = q = 1, ref2 = possible_turns; 1 <= ref2 ? q <= ref2 : q >= ref2; j = 1 <= ref2 ? ++q : --q) {
      guesses += this.nCk(i - 1, j - 1) * s * Math.pow(d, j);
    }
  }
  if (match.shifted_count) {
    S = match.shifted_count;
    U = match.token.length - match.shifted_count;
    if (S === 0 || U === 0) {
      guesses *= 2;
    } else {
      shifted_variations = 0;
      for (i = u = 1, ref3 = Math.min(S, U); 1 <= ref3 ? u <= ref3 : u >= ref3; i = 1 <= ref3 ? ++u : --u) {
        shifted_variations += this.nCk(S + U, i);
      }
      guesses *= shifted_variations;
    }
  }
  return guesses;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.zxcvbn.scoring.uppercase_variations"></a>[function <span class="apidocSignatureSpan">zxcvbn.scoring.</span>uppercase_variations (match)](#apidoc.element.zxcvbn.scoring.uppercase_variations)
- description and source-code
```javascript
uppercase_variations = function (match) {
  var L, U, chr, i, len, o, q, ref, ref1, regex, variations, word;
  word = match.token;
  if (word.match(this.ALL_LOWER) || word.toLowerCase() === word) {
    return 1;
  }
  ref = [this.START_UPPER, this.END_UPPER, this.ALL_UPPER];
  for (o = 0, len = ref.length; o < len; o++) {
    regex = ref[o];
    if (word.match(regex)) {
      return 2;
    }
  }
  U = ((function() {
    var len1, q, ref1, results;
    ref1 = word.split('');
    results = [];
    for (q = 0, len1 = ref1.length; q < len1; q++) {
      chr = ref1[q];
      if (chr.match(/[A-Z]/)) {
        results.push(chr);
      }
    }
    return results;
  })()).length;
  L = ((function() {
    var len1, q, ref1, results;
    ref1 = word.split('');
    results = [];
    for (q = 0, len1 = ref1.length; q < len1; q++) {
      chr = ref1[q];
      if (chr.match(/[a-z]/)) {
        results.push(chr);
      }
    }
    return results;
  })()).length;
  variations = 0;
  for (i = q = 1, ref1 = Math.min(U, L); 1 <= ref1 ? q <= ref1 : q >= ref1; i = 1 <= ref1 ? ++q : --q) {
    variations += this.nCk(U + L, i);
  }
  return variations;
}
```
- example usage
```shell
...
    }
  }
  return guesses;
},
dictionary_guesses: function(match) {
  var reversed_variations;
  match.base_guesses = match.rank;
  match.uppercase_variations = this.uppercase_variations(match);
  match.l33t_variations = this.l33t_variations(match);
  reversed_variations = match.reversed && 2 || 1;
  return match.base_guesses * match.uppercase_variations * match.l33t_variations * reversed_variations;
},
START_UPPER: /^[A-Z][^A-Z]+$/,
END_UPPER: /^[^A-Z]+[A-Z]$/,
ALL_UPPER: /^[^a-z]+$/,
...
```



# <a name="apidoc.module.zxcvbn.time_estimates"></a>[module zxcvbn.time_estimates](#apidoc.module.zxcvbn.time_estimates)

#### <a name="apidoc.element.zxcvbn.time_estimates.display_time"></a>[function <span class="apidocSignatureSpan">zxcvbn.time_estimates.</span>display_time (seconds)](#apidoc.element.zxcvbn.time_estimates.display_time)
- description and source-code
```javascript
display_time = function (seconds) {
  var base, century, day, display_num, display_str, hour, minute, month, ref, year;
  minute = 60;
  hour = minute * 60;
  day = hour * 24;
  month = day * 31;
  year = month * 12;
  century = year * 100;
  ref = seconds < 1 ? [null, 'less than a second'] : seconds < minute ? (base = Math.round(seconds), [base, base + " second"]) :
seconds < hour ? (base = Math.round(seconds / minute), [base, base + " minute"]) : seconds < day ? (base = Math.round(seconds /
hour), [base, base + " hour"]) : seconds < month ? (base = Math.round(seconds / day), [base, base + " day"]) : seconds < year ? (
base = Math.round(seconds / month), [base, base + " month"]) : seconds < century ? (base = Math.round(seconds / year), [base, base
 + " year"]) : [null, 'centuries'], display_num = ref[0], display_str = ref[1];
  if ((display_num != null) && display_num !== 1) {
    display_str += 's';
  }
  return display_str;
}
```
- example usage
```shell
...
    online_no_throttling_10_per_second: guesses / 10,
    offline_slow_hashing_1e4_per_second: guesses / 1e4,
    offline_fast_hashing_1e10_per_second: guesses / 1e10
  };
  crack_times_display = {};
  for (scenario in crack_times_seconds) {
    seconds = crack_times_seconds[scenario];
    crack_times_display[scenario] = this.display_time(seconds);
  }
  return {
    crack_times_seconds: crack_times_seconds,
    crack_times_display: crack_times_display,
    score: this.guesses_to_score(guesses)
  };
},
...
```

#### <a name="apidoc.element.zxcvbn.time_estimates.estimate_attack_times"></a>[function <span class="apidocSignatureSpan">zxcvbn.time_estimates.</span>estimate_attack_times (guesses)](#apidoc.element.zxcvbn.time_estimates.estimate_attack_times)
- description and source-code
```javascript
estimate_attack_times = function (guesses) {
  var crack_times_display, crack_times_seconds, scenario, seconds;
  crack_times_seconds = {
    online_throttling_100_per_hour: guesses / (100 / 3600),
    online_no_throttling_10_per_second: guesses / 10,
    offline_slow_hashing_1e4_per_second: guesses / 1e4,
    offline_fast_hashing_1e10_per_second: guesses / 1e10
  };
  crack_times_display = {};
  for (scenario in crack_times_seconds) {
    seconds = crack_times_seconds[scenario];
    crack_times_display[scenario] = this.display_time(seconds);
  }
  return {
    crack_times_seconds: crack_times_seconds,
    crack_times_display: crack_times_display,
    score: this.guesses_to_score(guesses)
  };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.zxcvbn.time_estimates.guesses_to_score"></a>[function <span class="apidocSignatureSpan">zxcvbn.time_estimates.</span>guesses_to_score (guesses)](#apidoc.element.zxcvbn.time_estimates.guesses_to_score)
- description and source-code
```javascript
guesses_to_score = function (guesses) {
  var DELTA;
  DELTA = 5;
  if (guesses < 1e3 + DELTA) {
    return 0;
  } else if (guesses < 1e6 + DELTA) {
    return 1;
  } else if (guesses < 1e8 + DELTA) {
    return 2;
  } else if (guesses < 1e10 + DELTA) {
    return 3;
  } else {
    return 4;
  }
}
```
- example usage
```shell
...
  for (scenario in crack_times_seconds) {
    seconds = crack_times_seconds[scenario];
    crack_times_display[scenario] = this.display_time(seconds);
  }
  return {
    crack_times_seconds: crack_times_seconds,
    crack_times_display: crack_times_display,
    score: this.guesses_to_score(guesses)
  };
},
guesses_to_score: function(guesses) {
  var DELTA;
  DELTA = 5;
  if (guesses < 1e3 + DELTA) {
    return 0;
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
